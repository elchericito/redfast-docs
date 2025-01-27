---
title: How can I debug a prompt that is not showing?
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
1. Make sure that the following conditions are met:

* The RF tag is running on the page you're trying to trigger a prompt. You can verify this by checking whether you receive ping calls on this specific page.
* The prompt status is 'Active'.
* The segment is configured on the prompt and it is enabled. 
* The user ID you're trying to trigger a prompt with is part of the targeted Segment (you can verify it in the ping call, by impersonating this user ID via the Preview tool or using the User Lookup feature under Settings -> Users)
* The trigger is configured on a prompt or a prompt is configured to trigger off interaction with a different prompt (i.e., within a survey guide) that is also Active. 
* The trigger criteria are met. For example, if a trigger is defined as a specific page, you are trying to trigger the prompt on this exact page. If a trigger is configured on a click of a specific element, make sure the element CSS class/ID matches the one configured in the trigger settings. 

2. If all of the above is in place, check if the prompt is being delievered in the Ping call. You should see it under **Paths**:

   <Image align="center" className="border" border={true} src="https://files.readme.io/73b7658-image.png" />
3. If the prompt is delivered but you still don't see it, check if there is an active experiment on the prompt with a control group and whether your user ID may be part of the control group. You can open the corresponding path and check the **action\_group\_name**. If it is set to "Control", this means that your user ID is held out of seeing the prompt by design.

   <Image align="center" className="border" border={true} src="https://files.readme.io/67a6aa2-image.png" />
4. If the prompt is not delivered, check if there are any limits set on the prompt (i.e., impression limit/frequency cap/ delivery limit) or any user interaction settings (i.e., “Show prompt again after button 1 click or button 2 click” under the prompt editor) that may prevent you from seeing a prompt again if you've already interacted with it previously. 

   If there are, and the user you're trying to see the prompt with has seen/interacted with it before, the prompt may not show up due to the limit reached. To reset the limit go to Console and run `Redfast.resetGoals(true)` followed by a few page refreshes.

   <Image align="center" className="border" border={true} src="https://files.readme.io/89184dd-image.png" />

If the prompt does not appear after all the steps above, reach out to your Redfast contact for support, and we'll help you get it solved.
