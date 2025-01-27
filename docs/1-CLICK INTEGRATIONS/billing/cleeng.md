---
title: Cleeng
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
## Required Settings

- API Key (Instructions [here](https://publisher.support.cleeng.com/hc/en-us/articles/218389137-Obtaining-your-API-Broadcaster-Token))

## Supported Actions

| Action                  | Description                                                   | Dependencies                                                 |
| :---------------------- | :------------------------------------------------------------ | :----------------------------------------------------------- |
| Switch Subscription     | Subscribe User to Different Offer                             | Offer Upgrade/Downgrade must be configured in Cleeng console |
| Apply Coupon            | Apply Coupon Code to Subscription                             |                                                              |
| Reactivate Subscription | Reactivate Subscription that has been marked for Cancellation |                                                              |

## Sync Subscription Data

It is recommended to schedule an automated data sync with Cleeng from the admin console.

<Image align="center" src="https://files.readme.io/217df5b-Screenshot_2024-06-02_at_10.08.45_PM.png" />



**Steps:**

1. Within the Cleeng console go to "Segments"
2. Click "Build a Segment" then click on the gear icon on the upper right
3. Click "Schedule" from the dropdown menu
4. Click "New". Give the schedule a name, i.e. "Redfast Sync"
5. Select "Amazon S3"
6. Fill out the Bucket, Optional Path, Access Key and Secret key information that available from the Settings &gt; User Traits &gt; AWS S3 Credentials section from Pulse. Select "US West (Oregion) - us-west-2" for the Region.
7. Select "CSV"
8. Trigger: "Repeating interval"
9. Deliver this Schedule: "Daily" &gt; "Every day". Select a time after midnight, i.e. 1:00AM.
10. Advanced Options
    1. Send this schedule if: "there are results"
    2. Check the box next to "and results changed since last run"
    3. Timezone: "United States - Los Angeles"
11. Select "Send Test" and work with your Customer Success Manager to confirm successful transmission
12. Make sure to "Save All" when complete