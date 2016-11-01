---
layout:     article
title:      How to get Google OAuth Client ID for web?
summary:    For payments to work securely, the user is authenticated using a Google account on the phone.
---
**Payments via Assistive Cards** is the most interesting feature of Horntell. Using it, your business can ask for payments via Cards themselves. Besides making payments easy and seamless experience, Horntell strives to keep the security around it top notch too.

For high security and therefore less fraud cases and chargebacks, we need you to generate a key in Google Cloud dashboard and pasting it in your Android app's `AndroidManifest.xml` file.

> **Note:** This step is highliy recommended but not required if you do not intend to accept payments via Cards.

Here's what you will need handy when creating Google OAuth Client ID for web:

- Package name of your Android app. *eg. com.example*

- SHA-1 signing-certificate fingerprint (explained below). *eg. 12:34:56:78:90:AB:CD:EF:12:34:56:78:90:AB:CD:EF:AA:BB:CC:DD*

Here's how to get the Google OAuth Client ID for web:

- Go to Google Cloud: [https://cloud.google.com](https://cloud.google.com).

- Sign in to **Console** by clicking the button in the top-right corner.

- You will land inside the console. Now, you need to head to the **API Manager** ([https://console.cloud.google.com/apis](https://console.cloud.google.com/apis). It can be found by clicking on the hamburger menu in the top-left corner.

- Go to the **Credentials** section from the menu on the left.

- If you haven't created any project before in Google Cloud, you will be prompted to create a new project right now. All it takes to create a project is the name of the project. Just put your app's name and hit **Create**.

- If you already have a project in Google Cloud related to your app, select the correct project from the drop down using the drop-down menu on the top.

- Once inside the **Credentials** section, you will need to create two credentials - one for Web and another for Android. Let's start by creating for Android. Click on the **Create credentials** button and select **OAuth client ID**.

- When creating the client ID, choose **Android**, give it a name (eg. Awesome App Android Client), enter the SHA-1 signing-certificate fingerprint and the package name.

	To get the SHA-1 signing-certificate fingerprint, you will need to use the Keytool utility.
	
	- Make note of keystore you are using to sign the `.apk`. You will need to specifically make note of the alias that you are using and the path to the keystore.
	
	- Run the following command in the terminal:
		
		```keytool -exportcert -alias <keystore_alias> -keystore <keystore_path> -list -v```
		
		For example, to get debug certificate fingerprint:
			
		```keytool -exportcert -list -v -alias androiddebugkey -keystore ~/.android/debug.keystore```
	
	- The keytool utility prompts you to enter a password for the keystore. The default password for the debug keystore is `android`. The keytool then prints the fingerprint to the terminal. For example:
		
		```Certificate fingerprint: SHA1: DA:39:A3:EE:5E:6B:4B:0D:32:55:BF:EF:95:60:18:90:AF:D8:07:09```

- Hit **Create**.

- Difficult part is done. We've create one OAuth client successfully. We'll need to create one more - for the web, and put its Client ID in the Horntell dashboard when enabling Payments for your account.

- Inside the **Credentials** section, click on the **Create credentials** button and select **OAuth client ID**.

- When creating the second client ID, choose **Web application**, give it a name (eg. Awesome App Web Client) and hit **Create**.

- We've both the client ID ready now. We'll need to copy the OAuth Client ID for the web and enter in the Horntell dashboard when enabling payments. And also add the following line with the correct value to your `AndroidManifest.xml`:
{% highlight xml %}
<meta-data
	android:name="HORNTELL_GOOGLE_OAUTH_WEB_CLIENT_ID"
	android:value="780816631155-gbvyo1o7r2pn95qc4ei9d61io4uh48hl.apps.googleusercontent.com"
/>
{% endhighlight %}

***
Now, you can go ahead and submit the details to us for review - post which, Payments will be enabled in your account.