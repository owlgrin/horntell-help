---
layout:     article
title:      Integration
summary:    There are just 3 important terms in Horntell around which our whole discussion will revolve.
---

#### Environments

You, as an user, can manage multiple apps under same account. And each app has two environments - LIVE (for production) and TEST (for development and testing).

Environments can be switched using the switch in the top-right corner.

![environment-variable]({{site.url}}/images/environment.png)

Let’s flip it into **test environment** and get going.

#### Integration

The important Keys and JS code snippet can be found in your account (under [APP] > Settings > Integrate): http://app.horntell.com/#/app/settings/integrate.

![integration-code]({{site.url}}/images/integration.png)

Integrate
You’ll need to paste in the similar looking JS code snippet in all webpages on which you need the notification center. Because notifications are user-specific, you’ll need to pass in a few parameters to give it knowledge about the user:

1. **uid**: The unique identifier of the logged in user in your system. (Primary Key)

2. **uid_hash**: HMAC SHA256 hash of uid using the app’s secret as the salt. (security reasons)

3. **signedup_at**: UNIX timestamp in UTC when the user signed up in your app.

Besides these required parameters, you can pass in additional optional data that will be added in the profile of the user. Why this additional data? Two reasons:

You can use this data to segment your users and do some bulk actions (eg. notifying everyone who is on GOLD plan).

You can use this data from your profiles to replace the variables in your campaigns/horns thus making a more personal impact.

The complete details about various attributes of profile can be found at: http://docs.horntell.com/api/#profiles