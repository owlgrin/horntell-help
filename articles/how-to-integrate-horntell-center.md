---
layout:     article
title:      How to integrate the JS widget (aka Horntell Center)?
summary:    Horntell Center is the real-time notification center that gets embedded on your site.
---
The powerful feature of Horntell is the web widget that can be placed on you website and can act as the notification center. Horntell Center listens for all the real-time notifications that are pushed from your backend and renders them on your site. Besides this, it also does a lot of non-onvious things like maintaining read/unread status of notifications, buffering unread notifications if you user is not currently online on your site, etc.

> **Tip:** It’s best to get your technology team do this integration for you. It will take a couple of minutes for them to do this.

1. When you first log in you account, you will see a switch in top-right corner of your account which lets you switch between **Live** and **Test** environments. Use test environment when working locally and live environment in production.
	![app-environments]({{site.baseurl}}/images/environment-switch.png)

2. Once the environment is set, you need to find the integration code by clicking on your app’s name in top-right corner and then clicking on **Settings**. Under the **Integrate** tab, you will find the API keys and integration code.
	![integration-keys]({{site.baseurl}}/images/integration-keys.png)

3. You will need to paste the widget code in the webpage where you want to show notifications. As the notifications are based on the logged-in user in your app, you will need to fill the values in these variables dynamically using the server-side language that you are using.

- **uid**: This is the unique identifier for the user in your app. (Primary Key)
- **uid_hash**: This is the HMAC SHA256 hash of profile’s uid with your app’s secret key.
- **signedup_at**: This is the UNIX timestamp (in UTC) of the user when she first signed up for your app.

4. Besides these required parameters, you can also send the optional data that you want to keep in the profile. More information about various profile attributes can be found at: [http://docs.horntell.com/api/#profiles](http://docs.horntell.com/api/#profiles).

_**Note:** In the JS code snippet, the variable `__ht.app` will already be initialized with correct value for your account. You do **NOT** need to alter this variable._
	![app-id-already-filled]({{site.baseurl}}/images/app-id-already-filled.png)