---
layout:     article
title:      How to integrate the Android SDK (aka Horntell Zed)?
summary:    Horntell Zed is the personal assistant that gets embedded in your app and delivers Assistive Cards.
---
The delivery mechanism of Assistive Cards is the personal assistant that Horntell creates for your Android app. Horntell Zed listens for all the real-time Assistive Cards that are pushed from your backend servers and delivers them to your users. Besides this, it also does a lot of non-onvious things like maintaining read/unread status of Cards, buffering unread Cards if your user is currently acting on any previous sent Card, etc.

> **Tip:** It’s best to get your technology team do this integration for you. It will take a couple of minutes for them to do this.

- When you first log in you account, you will see a switch in top-right corner of your account which lets you switch between **Live** and **Test** environments. Use test environment when working locally and live environment in production.
	![app-environments]({{site.baseurl}}/images/environment-switch.png)

- Once the environment is set, you need to find the integration code by clicking on your app’s name in top-right corner and then clicking on **Settings**. Under the **Integrate** tab, you will find the API keys and integration code.
	![android-integration-keys]({{site.baseurl}}/images/android-integration-keys.png)

- You will need to paste the code in the `build.gradle` file of the Android app. The latest version of Zed will be found in your account that will replace **X.Y.Z** in the code below.
{% highlight text %}
compile 'com.horntell:zed:X.Y.Z'
{% endhighlight %}

- As the Cards are pushed to the logged-in user in your app, you will need to initialize the SDK dynamically at the point where you authenticate your user. Make sure you calculate the "UID_HASH" at your server and send it in response to the user authentication call. Upon receiving this hash from the server, pass it to Horntell. DO NOT REVEAL the App's secret in your shipped app anywhere. (More about hashing is available [here](http://docs.horntell.com/api/#hashing)).
{% highlight java %}
Profile profile = new Profile();

// UID is the unique identifier for the user in your app. (Primary Key)
profile.setUid(/* UID */);

// UID_HASH is the HMAC SHA256 hash of profile’s uid with your app’s secret key.
profile.setUidHash(/* UID_HASH */);

// Additional Information to save for this profile.
profile.setEmail("email@example.com");

new Horntell(this, "/* APP_ID */", profile).start();
{% endhighlight %}

> **Tip:** In the code snippet, the variable `APP_ID` will already be initialized with correct value for your account. You do **NOT** need to alter this variable.

- Last step involves, generating a Google OAuth Web Client ID and adding it to your `AndroidManifest.xml` file. This is required because some of the actions in the Cards, like Payments, must be authenticated with the information present on the device (that is, the user's logged in Google account). You can follow the [steps to generate Google OAuth Web Client ID]({{site.baseurl}}/articles/how-to-get-google-oauth-client-id-for-web/) and then add the following line with the correct value to your `AndroidManifest.xml`:
{% highlight xml %}
<meta-data
	android:name="HORNTELL_GOOGLE_OAUTH_WEB_CLIENT_ID"
	android:value="780816631155-gbvyo1o7r2pn95qc4ei9d61io4uh48hl.apps.googleusercontent.com"
/>
{% endhighlight %}

***
Now, we've got the Horntell Zed integrated, we can [begin pushing Assistive Cards to our users]({{site.baseurl}}/articles/how-to-push-assistive-cards-from-dashboard).