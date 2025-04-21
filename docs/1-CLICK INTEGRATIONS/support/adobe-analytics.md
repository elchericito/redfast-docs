---
title: Adobe Analytics
deprecated: false
hidden: false
metadata:
  robots: index
---
For web based devices, Redfast utilizes the running instance of [Alloy.js](https://github.com/adobe/alloy?tab=readme-ov-file) . This ensures that session and user data context is maintained while reporting real-time Redfast prompt events.

**Event Details**

| Event Name                | Description                                                                                                                                    |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Redfast Prompt Impression | A user has seen the prompt                                                                                                                     |
| Redfast Prompt Dismiss    | A user has dismissed the prompt by clicking on the 'close'('X') button or outside the prompt view (if the 'Click outside to close' is enabled) |
| Redfast Prompt Timeout    | The prompt has been closed automatically due to close timer timeout (if set)                                                                   |
| Redfast Prompt Decline    | A user has declined the prompt by clicking on the decline button (Button 3)                                                                    |
| Redfast Prompt Click      | A user has accepted the prompt by clicking on the primary CTA button (Button 1)                                                                |

## Setup

Within Adobe, create a Datastream. This may require a report suite, schema, and field group. Enter the ID of the datastream within Settings -> Integrations -> External -> Adobe Analytics. Also enter the [org ID](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid)