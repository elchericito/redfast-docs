---
title: How should I test a prompt before launching?
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
The best way to test a prompt is to activate it on an internal segment called “[Test Users](test-users).”\
You can do this in your production environment as this will ensure that only user IDs added to the Test Users list will be eligible to see the prompt and QA the whole flow before launching to the actual targeted audience. 

If need be, you can also create a segment to target a single specific test user or group of test users by their User IDs:

<Image align="center" className="border" border={true} src="https://files.readme.io/ba8c882-image.png" />

Once the prompt is fully tested and validated, all the necessary adjustments and changes are made, you just need to update the segment on the prompt to the targeted segment, and the prompt will go live to a broader audience.

> 📘 If the test prompt only displays once:
>
> Keep in mind that while testing, you may need the prompt to display multiple times to the same user ID. To ensure the prompt shows up after a user clicks any CTA button or closes it, check the following settings:
>
> * **Interaction Settings:** Make sure the setting “Show prompt again after button 1 click or button 2 click” and/or “Show prompt again after button 3 click” under the “User Interaction” section in the prompt edit menu is set to "on the next visit" or " after X minutes/hours/days" if you want the prompt to reappear.
> * **Prompt Limits:** Verify that none of the prompt limits, such as impression limits, frequency caps, or delivery limits, are configured in a way that affects your testing.
>
> You can also reset user goals to simulate that the user did not perform any actions on the website. Navigate to Settings -> Users -> Test Users -> Reset Clicks in the Live tool, or use the `Redfast.resetGoals();` command in the browser’s developer console.
