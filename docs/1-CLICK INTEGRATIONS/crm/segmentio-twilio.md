---
title: Segment
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
## Integrating with Segment.com

Redfast allows you to ingest Segment.com events and target your users according to your existing Page (web), Screen (mobile), and Track calls. This article explains how to add us as as a destination via Amazon Lambda.

1. Login to Segment
2. Go to the correct app workspace\
   ![Settings→Integrations](https://files.readme.io/f5c742b-Segment_configure.png)
3. Add a new destination\
   ![Settings→Integrations](https://files.readme.io/125929e-Segment_configure_2.png)
4. Type lambda in the search box and click the found tile\
   ![Settings→Integrations](https://files.readme.io/cfe1f2f-Segment_configure_3.png)
5. Click "Configure Amazon Lambda"\
   ![Settings→Integrations](https://files.readme.io/8baf8c6-Segment_configure_4.png)
6. Select your app and click "Confirm Source"\
   ![Settings→Integrations](https://files.readme.io/ffd3c94-Segment_configure_5.png)
7. Now go to \[2] and locate the credentials to enter\
   ![Settings→Integrations](https://files.readme.io/58f7707-Segment_Configure_6.png)
8. Copy over the `Region`, `Role Address`  and `Lambda ARN` values.  Make sure to provide the read-only `External ID` to your customer success manager as the final step. Note that `Client Context` and `Log Type` do not need any special configuration.\
   ![Settings→Integrations](https://files.readme.io/a036acc-Segment_configure_7.png)\
   ![Settings→Integrations](https://files.readme.io/a6f4a75-Segment_Configure_8.png)

Information from Segment can take up to one hour before they are available within Redfast.

## Adding a new tracker

1. Go to Settings > Usage Tracking > Segment > Add New Tracker\
   ![Settings→Integrations](https://files.readme.io/47e233c-Segment_configure_9.png)

2. Select a Segment event\
   ![Settings→Integrations](https://files.readme.io/0caf0ba-Segment_configure_10.png)

3. Click Submit\
   ![Settings→Integrations](https://files.readme.io/8c96b24-Segment_Configure_11.png)\
   ![Settings→Integrations](https://files.readme.io/f74c2d1-Segment_Configure_12.png)

4. Go to add a new segment\
   ![Settings→Integrations](https://files.readme.io/8ec2610-Segment_Configure_13.png)

5. Now under the "Usage" tab you can see the newly added Segment trait you can target\
   ![Settings→Integrations](https://files.readme.io/0af69fd-Redfast_usage_4.png)
