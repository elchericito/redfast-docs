---
title: Google Analytics
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
# Client Integration

For web based devices, Redfast utilizes the running instance of the Google Analytics JS SDK. This ensures that session and user data context is maintained while reporting real-time Redfast prompt events. Enter your [GA Tag ID](https://support.google.com/analytics/answer/9539598?hl=en)  within Settings -> Integrations -> External within Pulse

**Event Details**

| Activity                  | Description                                                                                                                                    |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Redfast Prompt Impression | A user has seen the prompt                                                                                                                     |
| Redfast Prompt Dismiss    | A user has dismissed the prompt by clicking on the 'close'('X') button or outside the prompt view (if the 'Click outside to close' is enabled) |
| Redfast Prompt Timeout    | The prompt has been closed automatically due to close timer timeout (if set)                                                                   |
| Redfast Prompt Decline    | A user has declined the prompt by clicking on the decline button (Button 3)                                                                    |
| Redfast Prompt Click      | A user has accepted the prompt by clicking on the primary CTA button (Button 1)                                                                |
| Redfast Prompt Holdout    | A holdout user has triggered the prompt                                                                                                        |
| Redfast Prompt Click 2    | A user has accepted the prompt by clicking on the secondary CTA button (Button 2)                                                              |

The following attributes (if applicable) are sent with each custom event.

| Event Property   | Description                                                                           |
| ---------------- | ------------------------------------------------------------------------------------- |
| promo\_id        | A unique prompt identifier that can be found in the 'Prompt ID' field under 'Details' |
| promo\_name      | The name of the prompt                                                                |
| variation\_id    | A unique identifier of a prompt variation running within an experiment                |
| variation\_name  | The name of the prompt variation running within an experiment                         |
| event\_timestamp | The time when the activity occurred                                                   |

##

<br />

# Server Integration

## Create an action

Follow the steps to create an API action. This action should be a POST request. The required url is listed here.

<Image align="center" width="650px" src="https://files.readme.io/ebf7cc4-Google_Analytics_Custom_Action.png" />

### Specify the payload

Add parameters to the payload. These values can be static or dynamic. Supported parameters are described [here](https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters). Required parameters include `v` (protocol version), `tid` (web property ID), and `t` (hit type). Optional parameters include `cid` (client id), `ea` (event action), and `el` (event label).

### Add action to prompt or experience

Follow the steps here to [add the action](actions-1) to a prompt or experience.