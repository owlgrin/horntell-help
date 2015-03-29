---
layout:     article
title:      How to automatically open urgent notifications?
summary:    Somethings are not to be ignored. Make them notice.
---

Some notifications are urgent and must not be missed by your users. For example, you cannot miss out on notifying your users that their trial period is about to get over. For such moments, we give you **bubble** notifications.

Bubble notifications open up automatically when they are pushed to your users. This removed one extra step for your user to see the content, and thus, giving better results.

> **Tip:** Just because Bubble notifications give better results, it is **NOT** recommended to use these for everything. This will irritate your users and thus churning out.

1. [Login](http://app.horntell.com) to your account and click on the <i class="fa fa-bell"></i> icon on any profile. We'll notify our users to follow us on Twitter in this demo. We’ll embed the Follow button right inside the notification.

2. In the "Simple" tab, click on the "Advanced" to expand it. In the HTML section, click inside textarea and then click the **Toggle HTML** button to reveal the raw HTML area.

3. Paste the HTML between the lines in there.

	--------------------------------

	&lt;p&gt;There's an &lt;strong&gt;Easter Egg&lt;/strong&gt; hidden in Horntell's website. Did you find it yet? (Hint: &lt;img src=&quot;http://twemoji.maxcdn.com/36x36/1f60b.png&quot; style=&quot;font-family: inherit; font-size: 13px; line-height: 1.42857143;width:1.5em; height:1.5em;margin: 0 .05em 0 .1em;vertical-align: -0.1em;&quot;/&gt;)&lt;/p&gt;&lt;p&gt;Click to dismiss this and start hunting. &lt;img src=&quot;http://twemoji.maxcdn.com/36x36/1f44d.png&quot; style=&quot;font-family: inherit; font-size: 13px; line-height: 1.42857143;width:1.5em; height:1.5em;margin: 0 .05em 0 .1em;vertical-align: -0.1em;&quot;/&gt;&lt;/p&gt;

	--------------------------------

4. But wait, before sending, toggle the button against "Bubble" to "yes".
	![html-content-in-notification]({{site.baseurl}}/images/articles/bubble.png)

5. Hit **Send**.

6. Notification instead of coming inside the widget, should open up automatically. Did it?