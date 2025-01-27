---
title: 1-Click Resubscribe
excerpt: >-
  Use Redfast to make it easy for churned customers to restart their
  subscription
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Churned users visiting your website can be targeted in real-time and presented with a re-activation prompt. If their card information is available within your subscriber management system, they can be re-activated in 1-click. You can also configure this as a double opt-in guide, giving them a second prompt confirming they want to restart the subscription.

Using this approach, your business can recover 10% or more of churned users.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/c958740-Screenshot_2024-04-30_at_12.18.40_PM.png" />

<br />

***

> 👍 For best results, consider providing an incentive to the user for resubscribing

<br />

## Step-by-step

* [ ] Create a segment of Churned Users. You may also consider creating a separate segment for users in the Dunning state.

* [ ] Follow these instructions to [Create a Notification Prompt](create-a-pop-up) 

* [ ] Modify the headline and message, including any dynamic variables for personalization, such as first name

* [ ] Under Add Action, select your billing platform and specify the re-activation plan

* [ ] Additionally, specify when you would like the plan change to be effective

* [ ] Set the segment to **Test Users**.

* [ ] Set the trigger to activate on the home page of your site (usually '/')

* [ ] Set the prompt to start

* [ ] Add your user ID to the Test Users segment (Settings > Users > Test Users)

* [ ] Confirm that the prompt is triggered when visiting the homepage

* [ ] Update the targeted segments for this prompt to include Churned Users

<br />

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/embed/42ea0c623c0e48b98d77e1d992ed0686?sid=fb0b44f8-127c-4072-a45a-8e0fa757f6a2" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>
