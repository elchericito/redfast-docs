---
title: Amplitude
deprecated: false
hidden: true
metadata:
  robots: index
---
## Activation

<br />

## Events

### Outbound Events

For web based devices, Redfast utilizes the running instance of the Amplitude JS SDK to report client-side events. This ensures that session and user data context is maintained while reporting real-time Redfast prompt events. Contact your Customer Success Manager to confirm the details of your Amplitude JS SDK config and to enable the integration.

| Event Name                 | Description                                                                                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Redfast Prompt Impression  | A user has seen the prompt                                                                                                                     |
| Redfast Prompt Dismiss     | A user has dismissed the prompt by clicking on the 'close'('X') button or outside the prompt view (if the 'Click outside to close' is enabled) |
| Redfast Prompt Timeout     | The prompt has been closed automatically due to close timer timeout (if set)                                                                   |
| Redfast Prompt Decline     | A user has declined the prompt by clicking on the decline button (Button 3)                                                                    |
| Redfast Prompt Click       | A user has accepted the prompt by clicking on the primary CTA button (Button 1)                                                                |
| Redfast Prompt Custom Goal | A user has completed the set of actions / met the requirements to qualify for the custom goal completion (if a custom goal is set)             |

The following attributes (if applicable) are sent with each custom event.

| Event Property   | Description                                                                                              |
| ---------------- | -------------------------------------------------------------------------------------------------------- |
| app\_name        | The name of the application in your Pulse account                                                        |
| prompt\_id       | A unique prompt identifier that can be found in the 'Prompt ID' field under 'Details'                    |
| prompt\_name     | The name of the prompt                                                                                   |
| experiement\_id  | A unique experiemnt identifier                                                                           |
| experiment\_name | The name of the running experiment                                                                       |
| variation\_id    | A unique identifier of a prompt variation running within an experiment                                   |
| variation\_name  | The name of the prompt variation running within an experiment                                            |
| survey\_value    | A survey option value that has been selected and submitted (exists only if survey defined within prompt) |