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
