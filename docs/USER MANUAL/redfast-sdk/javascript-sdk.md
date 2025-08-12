---
title: JS (Web and CTV)
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
The Javascript SDK supports web browsers as well as HTML5 based CTV devices. To install the Javascript SDK, please visit this [article](add-the-redfast-tag).

## CTV Considerations

We recommend the following when integrating the JS SDK on CTV apps:

* Create a Custom Devices within Settings > Custom Devices. Multiple entries may be defined, e.g. `SamsungTV`, `LGTV`, `Vidaa`.
* Prompts should be created for the Custom Device(s). This allows for control over exactly which prompts are delivered to the various CTV platforms.
* The JS tag should specify the Custom Device representing the CTV platform. For example: `<script src="..." data-rf-device-type="SamsungTV" />`
* Ensure that the fetchUserId() functionality is integrated as this is often different than the normal Desktop/mobile web-app.
* As CTV apps are normall implemented as Single Page Apps, using prompts to navigate to specific screens may require a discussion with your dev team.
* Reach out to your Customer Success Manager if you have any questions!

## Analytics

While there are a number of built in integrations with Analytics services, you may want to generate a custom analytics payload to report all events relating to user interactions against Recurly Engage prompts. You may implement a callback function that is invoked whenever a user interaction occurs within Settings > Custom JS Snippet. Example code below:

```javascript
/*
  This function is called whenever a prompt event occurs, for custom analytics purposes
  @param {string} eventName: impression, click, click2, decline, dismiss, timeout, holdout
  @param {object} payload: {
    activity: "Redfast Prompt Click",
    cta: "CTA Button Text",
    el: <HTMLElement>,
    event_timestamp: "2025-01-01T08:00:00.000Z",
    promo_id: "abcd1234-1234-abcd-1234-abcdef123456",
    promo_name: "Prompt Name",
    user_id: "abcdef1234567890abcdef1234567890abcdef1234567890abcdef1234567890",
    variation_id: "abcd1234-1234-abcd-1234-abcdef123456",
    variation_name: "Experiment Name",
  }
*/
static onPromptInteraction(eventName, payload) {
  switch(eventName) {
    case "impression":
      myAnalytics.track("Prompt Impression", { "id": payload.promo_id, "name": payload.promo_name });
      break;
    case "dismiss"
      myAnalytics.track("Prompt Dismiss", { "id": payload.promo_id, "name": payload.promo_name });
      break;
  }
}
```