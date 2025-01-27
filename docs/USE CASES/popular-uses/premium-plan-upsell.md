---
title: Premium Plan Adoption
excerpt: How to use Redfast to increase the adoption of add-ons and premium plans
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Most subscription businesses use outbound email campaigns to inform users about premium plans and add-ons. While this can work with your highly engaged users, your casual users require context to establish relevance for why they should make this purchase.

Redfast provides a highly personalized approach to getting your users to purchase add-ons and premium plans. By targeting users on the site who have not purchased the add-on or the premium plan with a prompt, you can provide the user with greater context. You can further increase the context by creating a trigger based on a screen or event on the site that can be used to show the prompt.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/b953f97-Screenshot_2024-04-22_at_4.48.39_PM.png" />

<br />

***

## Step-by-step

* [ ] Modify the `Engaged Users` segment to target users on the monthly subscription plan

* [ ] Follow these instructions to [Create a Popup Prompt](create-a-pop-up) 

* [ ] Modify the headline and message, including any dynamic variables for personalization, such as first name

* [ ] Under Add Action, select your [Billing](billing) platform and specify the plan that the user should be upgraded to

* [ ] Additionally, specify when you would like the plan change to be effective

* [ ] Set the segment to **Test Users**.

* [ ] Set the trigger to activate on the home page of your site (usually '/')

* [ ] Set the prompt to start

* [ ] Add your user ID to the Test Users segment (Settings > Users > Test Users)

* [ ] Confirm that the prompt is triggered when visiting the homepage

* [ ] Update the targeted segments for this prompt to include `Engaged Users`

<br />

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;"><iframe src="https://www.loom.com/embed/c977818bce834868ae954663a38083f2?sid=6e1c0360-be70-4276-ba3e-38d96ed60a1b" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>
