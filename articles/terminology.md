---
layout:     article
title:      Terminology
summary:    However, we've kept all the jargon away, knowing these important terms will always keep us on the same page.
---

There are just a handful important terms in Horntell around which our whole discussion will revolve. They are:

**App**: One Horntell account can be used for more than one web app. Each such web app that you configure in your account is called an **app** in Horntell.

**Environment**: We understand that before pushing the integration in public, you'd like to test it out in your development environment. Therefore, each app comes with two environments - LIVE (for production) and TEST (for development/testing). The two environments run independently of each other and the data between them is not shared.

**Profiles:** Notifications are user-specific. Your every user has a corresponding profile created in Horntell account. A **user** in your app is called a **profile** in Horntell.

**Horns:** These are the push notifications in Horntell’s terms. We got tired of typing out the long word **notifications** over and over again, and thus decided to cut a few keystrokes short. ;)

**Campaigns:** In our beta, we found our users hardcoding the notification’s content in their codebase. This meant that to change the content, they’d to go through the long shipping cycle. Ugh! Using campaigns, you can save the content of the horn in your dashboard as a template and put the identifier of the campaign in your codebase. Need to change the content? Do it on the fly from your dashboard. Sweet!

**Segments:** Segments are the group of users that share some common characteristics. We have put the following segments in your Horntell account for each app:

- **All**: everyone.
- **New**: everyone who signed up less than 3 days ago.
- **Active**: everyone who signed up more than 30 days ago but was last seen less than 3 days ago.
- **Slipping Away**: everyone who signed up less than 30 days ago but was last seen more than 7 days ago.
- **Lost**: everyone who was last seen more than 30 days ago.

_**Note:** We may open up feature to create your own custom segments in future._
