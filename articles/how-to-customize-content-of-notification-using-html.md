---
layout:     article
title:      How to customize content of notification using HTML?
summary:    Why send just text, when you can send emoticons? ;)
---
We allow you to build your notifications in pure HTML (of course, we will not allow some tags like `<form>`, but besides those, you can do anything with them.)

If you're reading it, we'll assume that you already know [how to push simple notifications]({{site.baseurl}}/articles/how-to-push-notifications-from-dashboard). This article will help you understand how to spice up your notifications so that they don't look so 1990s.

1. [Login](http://app.horntell.com) to your account and click on the <i class="fa fa-bell"></i> icon on any profile. We'll notify our users to follow us on Twitter in this demo. We’ll embed the Follow button right inside the notification.

2. In the "Simple" tab, click on the "Advanced" to expand it. In the HTML section, click inside textarea and then click the **Toggle HTML** button to reveal the raw HTML area.

3. Paste the HTML between the lines in there.

	--------------------------------

	&lt;p&gt;&lt;b&gt;You're our most active user last month.&lt;/b&gt; I thought, may be you'd like to stay connected with us on Twitter.&lt;/p&gt;&lt;p style=&quot;font-family: courier;&quot;&gt;- Mohit (CEO, Horntell)&lt;/p&gt;
	&lt;iframe src=&quot;//platform.twitter.com/widgets/follow_button.html?screen_name=<span style="color:#E76A11;">horntell</span>&amp;amp;show_count=false&quot; allowtransparency=&quot;true&quot; frameborder=&quot;0&quot; scrolling=&quot;no&quot; style=&quot;font-family: inherit; line-height: 1.42857143; width: 150px; height: 20px;&quot;&gt;&lt;/iframe&gt;

	--------------------------------
	![html-content-in-notification]({{site.baseurl}}/images/articles/html.png)

> **Tip:** You can change the part in red color with your own Twitter handle.

4. Hit **Send**. Did you get the notification? Isn't it awesome?