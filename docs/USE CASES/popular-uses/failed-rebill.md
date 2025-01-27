---
title: Failed Rebill
excerpt: How to use Redfast to reduce active cancellations (voluntary churn)
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
A common problem with subscription businesses is when an attempt to bill the customer fails. This can happen due to various reasons such as expired cards, fraud, or spending limits. While your payment processor may offer some black box processes to remedy this issue, only a tiny percentage are recovered using this approach.

Redfast provides an additional tool to reduce involuntary churn by using a guide to prompt the user over one or more visits to update their payment information.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/0d72e3a-image.png" />

<br />

> 📘 Make sure you check the 'Sync events' option, if available, for your billing platform under Settings > Actions. This ensures that updates from dunning processes are synced with the Redfast segments.

***

## How-to video

Here is a video tutorial that shows how to set this up for your website and app.

<br />

<Embed url="https://www.loom.com/embed/d1c5c4f59f7a4b23a5e99e92c1381b8b?sid=2ea41637-d7ec-4f32-b722-0c1bceb4d91b" title="iframe" provider="loom.com" href="https://www.loom.com/embed/d1c5c4f59f7a4b23a5e99e92c1381b8b?sid=2ea41637-d7ec-4f32-b722-0c1bceb4d91b" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

<br />

***

## Step-by-step

* [ ] Follow these instructions to [Create a Guide](guides) and set the type to **Journey**
* [ ] Set the first prompt to a Notification prompt type that is shown when the first attempt to rebill has failed
* [ ] Set the CTA for this prompt to redirect to your payment update screen
* [ ] Create an A-B experiment on any of the prompts in the guide to experiment with offers or design.
* [ ] Set the segment to **Test Users**.
* [ ] Set the trigger to activate on Any Page (this may be changed later)
* [ ] Start the Guide
* [ ] Add your user ID to the Test Users segment (Settings > Users > Test Users)
* [ ] Confirm that the Guide is triggered as configured
* [ ] Change the targeting for this prompt to be members with failed payment

<br />

> 📘 If you connect Redfast to Recurly, the Failed Payment segment will be automatically created
