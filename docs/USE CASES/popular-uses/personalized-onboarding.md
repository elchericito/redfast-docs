---
title: Personalized Onboarding
excerpt: Use Redfast to onboard new and existing users in a personalized manner
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: See more popular uses
  pages:
    - type: basic
      slug: popular-uses
      title: Popular Uses
---
Traditional approaches to onboarding new users include a step-by-step home page tour with highlighted callouts to various features. This method is relevant for B2B sites or apps, but B2C service users find it annoying as it impedes their flow. 

Redfast's Journey guide is a breakthrough new approach to onboarding users in a personalized and contextual manner. Here is how it works.

Even before a new user arrives on the site, a Redfast guide is configured with links to the key elements of the site and the order in which they should be presented to the end user. Further, the elements are only shown to the user if they have not visited that section or performed the desired action. Lastly, the prompts in this guide can be configured to be shown over multiple visits. All of this produces a much more user-friendly approach to the challenge of educating and informing new users.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/8e77a00-Screenshot_2024-04-19_at_1.33.00_PM.png" />

<br />

> 📘 Create trackers for key features and content of your site and use them in an onboarding guide to only target users that have not accessed those items.

***

## Step-by-step

* [ ] Follow these instructions to [Create a Guide](guides) and set the type to **Journey**
* [ ] Set the first prompt to be a popup prompt to be shown to first-time users
* [ ] Set the CTA for this prompt to either 1-click trigger the feature/content or redirect
* [ ] Set the second prompt in the guide to show on the next visit
* [ ] Set the third prompt to show on the subsequent (or later) visit
* [ ] Set the segment to **Test Users**.
* [ ] Set the trigger to activate on one or more page URLs of your site
* [ ] Start the Guide
* [ ] Add your user ID to the Test Users segment (Settings > Users > Test Users)
* [ ] Confirm that the Guide is triggered as configured

<br />

> 📘 Switching up the order of your unique selling propositions can be done via an A-B experiment
