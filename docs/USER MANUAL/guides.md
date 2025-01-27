---
title: Guides
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
A guide is a collection of prompts that appear one after another. They can be connected across screens of an app/site or across devices. Guides can be used to onboard users, conduct surveys, persist offers or announcements, and reinforce messaging. All in a highly contextual and personalized manner. 

<Image align="center" className="border" border={true} src="https://files.readme.io/bd78e59-image.png" />

## Wizard

Supported device platforms: Web, HTML5 based smart TVs

This is commonly used for various step-by-step prompts. An example use case for this type of guide is a confirmation message that is shown after a pop-up is accepted.

* Prompts are shown immediately in the set order within one session.
* The trigger is only set up for the first prompt, and the rest of the prompts are triggered right away by interaction with the previous prompt.

 Items within a guide will also inherit the following configurations from the guide: [Limits](limits-1), [Segments](segments), [Schedule](schedule-1)

<Image align="center" className="border" border={true} src="https://files.readme.io/8a86d2f-image.png" />

## Survey

Supported device platforms: Web, HTML5 based smart TVs

This is commonly used for conditional cancellation flows. Prompts within a survey may be branched based on the user's input on the first prompt. 

![](https://files.readme.io/e09a8bd-image.png)

## Journey

Supported device platforms: All

This is the most commonly used for user onboarding. For example, you can create a journey to onboard new users to the various features of your app in a personalized manner as they visit various areas within your app. 

The guide can be configured to only show the items the user has not tried. You can also configure an ordered guide to make sure the user receives items in the specified order. For example you engage a user with an offer in different parts of an app over a period of time.

![](https://files.readme.io/9a5b99e-image.png)

Items within a guide can be connected with each other based on:

* **Interactions**. Make an item contingent on whether another item in the guide has been seen, accepted, declined, or dismissed by the end user.
* **Next Visit**. Create a guide to be shown to the user based on the on the next visit to your app across devices.
* **Days**. Create a guide to be shown to the user based on the number of days between user visits your app across devices.
* **Minutes**. Create a guide to be shown to the user based on number of minutes within a single session on a device.

<Embed url="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075" provider="loom.com" href="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" title="undefined" />

## Triggered

Supported device platforms: All

Typically used to reinforce a message or action that you would like the user to take. For example, you can configure an unordered guide to provide a user with an incentive to upgrade their plan with two prompts within the guide. You may start with an inline banner in one area and a popup in another area. The popup is shown only if the user has not seen or interacted with the inline banner. Additionally, if the user has seen or interacted with the prompt on one device then you may configure it to not show on other devices.

You can configure a set of conditions on each item within an unordered guide that will make the user ineligible to receive the other items within the same guide. This prevents the user from receiving similar items multiple times. 

<Image align="center" className="border" border={true} src="https://files.readme.io/831f597-image.png" />

## How-to-video

Here is a video tutorial that shows how to set up a Journey guide.

<Embed url="https://www.loom.com/embed/d1c5c4f59f7a4b23a5e99e92c1381b8b?sid=2ea41637-d7ec-4f32-b722-0c1bceb4d91b" provider="loom.com" href="https://www.loom.com/embed/d1c5c4f59f7a4b23a5e99e92c1381b8b?sid=2ea41637-d7ec-4f32-b722-0c1bceb4d91b" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" title="undefined" />

## Step-by-step

* [ ] Go to Guides > New Guide
* [ ] Enter name and description (optional). Select the guide type. Select segment(s)\
  In this case, we create a journey guide. Note that guide type cannot be changed after creation.
* [ ] Add at least two items.
* [ ] Set continue and exit conditions
* [ ] Add limits and schedule (optional)
* [ ] That’s it!\
  Once you are satisifed with your configurations, set the guide status to ‘Start’. Your guide has been created and is now live.
