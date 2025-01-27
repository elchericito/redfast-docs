---
title: mParticle
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
## Activation

You may activate the mParticle connector with the following steps:

1. Within your mParticle console, visit Setup > Inputs. You should see a screen like below.\
   ![Setup->Inputs](https://files.readme.io/d0f22ee-mParticle_add_new_custom_feed.png)
2. Click on "Feeds tab". Add a Custom Feed by clicking on the `+` icon on the right.
3. Set a Configuration Name for your Custom Feed.\
   ![Feeds](https://files.readme.io/9b94f9b-mParticle_add_new_custom_feed_1.png)
4. Please provide the Server Key, Server Secret and API endpoint to your Redfast Customer Success manager.\
   ![Key and Secret](https://files.readme.io/27a2abc-mParticle_add_new_custom_feed_2.png)

### Required Settings

* Base API endpoint (including Pod)
* Server Key and Server Secret
* Production or Development mode

### Supported Actions

| Action        | Description                                                                    |
| ------------- | ------------------------------------------------------------------------------ |
| Export Events | Reports custom events with the user-specific prompt interaction and attributes |

## Custom Events and Attributes

Once we have activated the integration, custom events will be reported to your mParticle account.

The custom events are tagged with their respective "Customer ID" identity, so you may review all of the events within the mParticle User Activity screen.

![User Activity](https://files.readme.io/b504573-mparticle-user-activity-4.png)\
![Custom Event](https://files.readme.io/e006d0a-mparticle-custom-event-5.png)

| Custom Event               | Description                                                                                                                                    |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Redfast Prompt Impression  | A user has seen the prompt                                                                                                                     |
| Redfast Prompt Dismiss     | A user has dismissed the prompt by clicking on the 'close'('X') button or outside the prompt view (if the 'Click outside to close' is enabled) |
| Redfast Prompt Timeout     | The prompt has been closed automatically due to close timer timeout (if set)                                                                   |
| Redfast Prompt Decline     | A user has declined the prompt by clicking on the decline button (Button 3)                                                                    |
| Redfast Prompt Click       | A user has accepted the prompt by clicking on the primary CTA button (Button 1)                                                                |
| Redfast Prompt Custom Goal | A user has completed the set of actions / met the requirements to qualify for the custom goal completion (if a custom goal is set)             |

The following attributes (if applicable) are sent with each custom event.

| Custom Attribute | Description                                                                                              |
| ---------------- | -------------------------------------------------------------------------------------------------------- |
| app\_name        | The name of the application in your Pulse account                                                        |
| prompt\_id       | A unique prompt identifier that can be found in the 'Prompt ID' field under 'Details'                    |
| prompt\_name     | The name of the prompt                                                                                   |
| experiement\_id  | A unique experiemnt identifier                                                                           |
| experiment\_name | The name of the running experiment                                                                       |
| variation\_id    | A unique identifier of a prompt variation running within an experiment                                   |
| variation\_name  | The name of the prompt variation running within an experiment                                            |
| survey\_value    | A survey option value that has been selected and submitted (exists only if survey defined within prompt) |

## Additional Information

[mParticle Custom Feed Reference](https://docs.mparticle.com/integrations/custom-feed/feed/)
