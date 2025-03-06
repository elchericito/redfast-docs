---
title: Adobe
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
**Adobe Experience Platform (AEP)**

The Redfast AEP connector pushes Redfast prompt interaction events to an Adobe [Data Stream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview). Events include impressions, goals, declines, dismisses, timeouts, custom\_goals, holdouts.

Configure the following objects within AEP

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

Input the following information within Pulse -> Settings -> Integrations -> External -> Adobe

* Identity Map Symbol
* [Event Type](https://github.com/adobe/xdm/blob/master/docs/reference/classes/experienceevent.schema.md#xdmeventtype-known-values) . Use a known event type or create a new one.
* Adobe Instance Name. The name of your Adobe Instance, for example `_production`. Viewable in the details of the schema
* Data Stream Id

<br />

Sample Schema with required fields, Adobe Instance Name, and profile toggle

<Image align="center" src="https://files.readme.io/6fb869da2965a8f79d20ef00ec618c6537524de444351e992c8df3bcd0fbbe46-Screenshot_2025-03-06_at_9.56.33_AM.png" />