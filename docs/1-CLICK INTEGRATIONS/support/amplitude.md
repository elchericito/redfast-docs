---
title: Amplitude
deprecated: false
hidden: false
metadata:
  robots: index
---
## Outbound Events

For web based devices, Redfast utilizes the running instance of the Amplitude JS SDK. This ensures that session and user data context is maintained while reporting real-time Redfast prompt events. Contact your Customer Success Manager to confirm the details of your Amplitude JS SDK config and to enable the integration. Input the [API key](https://amplitude.com/docs/apis/authentication)  in Settings -> Integrations -> External -> Amplitude within Pulse.

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

## Inbound Data Sync

Depending on use case, Event as well as User data may be synced via one of the following methods. We recommend discussing with your Customer Success Integration Specialist to determine the best integration method.

### CSV Export

One-off report exports can be downloaded from Amplitude and uploaded to Pulse. Please ensure that the User ID is the first column of the CSV export.

### Webhook

You may want to report certain events to be synced in real-time, for example, user activity like new signups, user property updates or cohort assignments.

1. Add a new Webhook destination from your Data Catalog
2. Your Customer Success Integration Specialist will provide the endpoint details. In most cases the default Amplitude Event payload is sufficient
3. Configure the webhook to filter for only events that are necessary to power your intended use cases
4. Click on "Test Connection" to validate the configuration

### Export API

For recurring CSV exports that require automation, Redfast uses the Export API to run scheduled exports and initiate syncs with Redfast. Please ensure that you share an API key with appropriate permissions and work with our Customer Success team to setup the automation.