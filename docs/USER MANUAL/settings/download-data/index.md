---
title: Download Data
excerpt: Downloading prompt activity data from Redfast
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Redfast can export data to various external systems. The simplest option is a CSV export of Segment, Prompt, and Guide data.

More advanced options to receive event data and syncing with an external reporting system like Google Analytics are also possible.

# Download from Pulse

See this [article](/docs/can-i-download-prompt-interactions-data#detailed-activity-data) for instructions on how to download activity data directly from Pulse.

# Download from AWS S3

Data from all user activity relating to running prompts are continuously saved to an AWS S3 bucket. This data may be imported into your BI system for offline analysis.

1. Go to Settings &gt; User Traits
2. Select “Click here for AWS S3 credentials”

<Image align="center" src="https://files.readme.io/60d5733d567e8ebe61eeef8a39345ccf6c7c78e00d792a40bf4f185f6db46108-aws-creds.png" />

3. You will need to copy the AWS Bucket, Access Key and Secret Key to login. Replace `ingest` with `exports` within the Upload Location path. All filenames will start with the activities prefix.

## Prompt Activity Data Specifications

| Field                     | Description                                                | Notes                                                         |
| ------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------- |
| app_id                    | Redfast app id                                             | Assigned by Redfast                                           |
| app_name                  | Redfast app name                                           | Name as saved within Settings &gt; Application                |
| activity                  | Type of activity                                           | Values: impression, timeout, dismiss, decline, click, exclude |
| user_id                   | Unique ID of user                                          |                                                               |
| anonymous_user_id         | Identifier for a user in the event userId is not available |                                                               |
| promo_id                  | Unique ID of prompt                                        | Assigned by Redfast                                           |
| promo_name                | Name of prompt                                             | As configured in Redfast Console                              |
| experiment_id             | Unique ID of experiment                                    | Only populated if there is a running experiment               |
| variation_id              | Unique ID of variation                                     | Only populated if there is a running experiment               |
| variation_name            | Name of variation                                          | Only populated if there is a running experiment               |
| survey_option             | Survey option label                                        | Only populated for survey prompts                             |
| ts                        | Timestamp that activity occurred                           | Epoch                                                         |
| pipeline_stage_start_id   | Unique ID of pipeline stage                                | Populated as part of Pipeline_Transition activity (optional)  |
| pipeline_stage_start_name | Name of pipeline stage                                     | Populated as part of Pipeline_Transition activity (optional)  |
| pipeline_stage_end_id     | Unique ID of pipeline stage                                | Populated as part of Pipeline_Transition activity (optional)  |
| pipeline_stage_end_name   | Name of pipeline stage                                     | Populated as part of Pipeline_Transition activity (optional)  |