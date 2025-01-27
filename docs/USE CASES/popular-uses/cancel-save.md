---
title: Cancel Save
excerpt: How to use Redfast to reduce active cancellations (voluntary churn)
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Check out other popular uses for Redfast
  pages:
    - type: basic
      slug: popular-uses
      title: Popular Uses
---
One of the most popular uses of Redfast is intercepting the cancel button click and presenting the user with a personalized offer.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/ba41c6a-Screenshot_2024-04-05_at_2.52.10_PM.png" />

<br />

> 📘 When combined with [1-click](actions-1), you can expect significant reductions in cancellations with improved customer satisfaction.

***

## How-to video

Here is a video tutorial that shows how to set this up for your website and app.

<br />

<Embed url="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286 nJvsnLtmKCrXY4dDsfkpywOr4wmdOyAf" title="iframe" provider="loom.com" href="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286 nJvsnLtmKCrXY4dDsfkpywOr4wmdOyAf" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

***

<br />

> 🚧 Note: Conversions are significantly lower when using a redirect URL instead of 1-Click actions

<br />

## Step-by-step

* [ ] Enable [1-Click Actions](actions-1) by activating the connector to your [Billing](billing) platform.
* [ ] Alternatively, you can specify a redirect URL to an existing screen.
* [ ] Follow these instructions to [Create a Guide](guides) and set the type to **survey**
* [ ] Add or modify the options on the reasons for cancellation screen. The following three options are standard:
  * [ ] Too expensive with CTA to a save offer
  * [ ] Not enough content with CTA to save offer or the latest content
  * [ ] Technical issues with CTA to support
* [ ] Create an A-B experiment on any of the prompts in the guide to experiment with offers or design.
* [ ] Set the segment to **Test Users**.
* [ ] Set the trigger to activate using the cancel button click. 
  * [ ] The 'Live' feature can detect and add the cancel click event. See how.
  * [ ] Invite a member of your development team to specify the click event using regex or Javascript.
* [ ] Start the Guide
* [ ] Add your User ID to the Test Users segment (Settings > Users > Test Users)
* [ ] Confirm that the Guide launches when you click on cancel

<br />

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/embed/3a55570da3084432bf8516b442ab5590?sid=80617f1e-c3be-4bc3-b322-99d6ad886dee" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>