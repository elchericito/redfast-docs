---
title: Adobe
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adobe AEP AJO
  description: ''
  keywords:
    - Adobe
    - AEP
    - AJO
    - Experience Manager
  robots: index
next:
  description: ''
---
## Adobe Experience Platform (AEP)

The Redfast AEP connector pushes Redfast prompt interaction events to an Adobe [Data Stream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview). Events include impressions, goals, declines, dismisses, timeouts, custom\_goals, and holdouts.

**Configure the following objects within AEP**

* [Identity Map](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/map-identities). Create an identity map or use an existing one.
* [Schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition). Enable the Profile toggle to view incoming data in real time from the Profiles section. Add the following traits to the schema within a [Field Group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/field-groups)
  * activity (String). The type of activity being reported, for example: "impression"
  * app\_id (String). The id of the Pulse instance
  * app\_name (String). The name of the Pulse instance
  * event\_timestamp (DateTime). The timestamp when the activity occurred
  * promo\_id (String). The id of the Redfast prompt
  * promo\_name (String). The name of the Redfast prompt
  * variation\_id (String). The id of the Redfast experiment variation (if applicable)
  * variation\_name (String). The name of the Redfast experiment variation (if applicable)
* Data stream. Add the schema to the data stream
* [Dataset](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) . Select the schema from the previous step. Enable the Profile toggle to view incoming data in real time from the Profiles section.

<br />

**Input the following information within Pulse -> Settings -> Integrations -> External -> Adobe**

* Identity Map Symbol
* [Event Type](https://github.com/adobe/xdm/blob/master/docs/reference/classes/experienceevent.schema.md#xdmeventtype-known-values) . Use a known event type or create a new one.
* Adobe Instance Name. The name of your Adobe Instance, for example `_production`. Viewable in the details of the schema
* Data Stream Id

<br />

**Sample Schema with required fields, Adobe Instance Name, and profile toggle**

<Image align="center" src="https://files.readme.io/6fb869da2965a8f79d20ef00ec618c6537524de444351e992c8df3bcd0fbbe46-Screenshot_2025-03-06_at_9.56.33_AM.png" />

## Adobe Journey Optimizer (AJO)

Your journey can sync updates to Redfast via a custom HTTP request, which allows you to update audience information as well as trigger in-app prompts for your targeted audience.

Before proceeding, consult with your Customer Success Manager with your intended set of use cases so that Redfast can provide guidance on the necessary endpoints and params to be configured within the custom HTTP request.

Once provided the endpoint information, you may create the custom action as follows:

1. Navigate to **Actions** within Adobe Journey Optimizer
2. Click **Create Action** and choose **Custom HTTP Action**
3. Provide a Name and Description for the action
4. In the Endpoint Configuration section:
   1. Set HTTP method to **GET**
   2. Enter the API endpoint
   3. Configure the query params which include one or more property key names along with their associated values. The convention is: properties\[**keyName**]=**value**
   4. Specify the `USER-ID` HTTP header
5. Test the Custom HTTP Action - your Customer Success Manager will confirm that the action processed successfully
6. Deploy the Action in AJO
   1. Save the Action
   2. Add it to your customer journey
   3. Monitor incoming requests to verify successful integration

Once the Custom HTTP Action is running within your journeys, the specified property name and values will be synced in real-time with Redfast for the specified user. This allows you to create user segments utilizing these properties and target specific prompts to be triggered when users are within your apps.

## Adobe Analytics

Redfast can send prompt interaction events via the Adobe Experience Platform Web SDK (alloy.js) for users on your web platforms. These events include impressions, goals, declines, dismisses, timeouts, custom\_goals, and holdouts. Contact your Customer Success Manager for instructions to enable this feature, as there is some configuration required before events can be sent to your data stream.