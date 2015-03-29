---
layout:     article
title:      How to iterate with notifications faster using Campaigns?
summary:    Hardcoding content of notification in your code, slows down the iteration cycle. Let's fix it!
---

We've an [API endpoint](http://docs.horntell.com/api/#horns), which can be used to send horns to single or multiple profiles, but it ahs a major drawback.

There's a problem when you hard-code the content of horns in your codebase, commit it and push it to production. The problem is that, if you want to change the content of horns, you’ll have to repeat the whole cycle of **code - commit - ship** to get it done. This sucks. And campaigns solve this problem.

Campaigns allow you to keep the horns stored as templates in your account and when you need to send a horn, simply use API endpoint to run a particular campaign. This has two benefits over hard-coding horn’s data in the codebase:
	- You can modify horn's content really quickly from your Horntell dashboard - without touching your codebase ever.
	- The stats to all the horns under one campaign can be seen together for analysis.

Here's how to create a campaign.

1. After [logging in](http://app.horntell.com) your Horntell account, go to the **Campaigns** section from the menu on the left hand side.

2. Hit the **Create New** button.

3. The wizard is a three step process. We'll start by entering the name and description of the campaign.
	![campaign-intro]({{site.baseurl}}/images/articles/campaign-intro.png)

4. Then, we will define the template of horn. Remember, you can add the variables that you store in the profile object for each user. This way, horns can be personalised.
	![campaign-horn]({{site.baseurl}}/images/articles/campaign-horn.png)

5. Finally, when you are satisfied with your campaign, review it and run it. Campaigns can be in two states, "stopped" and "running". Only the running campaigns can be fired using API/dashboard.
	![campaign-review]({{site.baseurl}}/images/articles/campaign-review.png)

6. Now, the created campaign can be fired for single or multiple profiles using this [API endpoint](http://docs.horntell.com/api/#campaigns) or from dashboard using the steps below.
	1. Go to any profile and hit the <i class="fa fa-rocket"></i> icon to fire a campaign for that profile.
	2. In the small window that opens up, press the **Trigger** button corresponding to the campaign you want to fire.