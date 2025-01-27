---
title: Event API Firehose
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
# S3 Event Data Logs

Usage tracking data that has been enabled in Redfast can be pushed to external systems. This means anything that is added to the Usage Tracker section will be sent out as an event once the integration is setup.

<Image align="center" src="https://files.readme.io/d7f9c3c-Event_Export_1.png" />

There are two ways to receive usage data. You must provide each the following values to your account manager for integration.

1. AWS S3 Requirements - Pull data using Redfast

   1. Go to Settings > User Traits  
      ![AWS Settings](https://files.readme.io/bfbf239-Event_Exports_settings.png)

   2. Select “Click here for AWS S3 credentials”  
      ![AWS Settings](https://files.readme.io/a970314-Event_Exports_settings_1.png)

   3. You will need to copy the AWS Bucket, Access Key and Secret Key to login. Navigate to the exports folder. All filenames will start with the `usages` prefix. You can pull this data whenever desired.

## AWS S3 Data Specifications

All data is JSON formatted with the following fields. To enable optional fields please ask your account manager:

| Field              | Description                                                                                 | Notes                                             |
| ------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| user_id            | Primary user identifier                                                                     |                                                   |
| anonymous_user_id  | Identifier for a user in the event userId is not available                                  |                                                   |
| event              | Name of event                                                                               | Name of event being exported                      |
| platform           | Type of integration                                                                         | Always redfast for usage                          |
| type               | Type of tracker                                                                             | Types: page, track, custom                        |
| properties.id      | Usage Tracker id                                                                            |                                                   |
| properties.values  | Configured in Redfast Console                                                               |                                                   |
| properties.options | Additional options                                                                          | Specifies if Regex is used for page type trackers |
| ts                 | Timestamp that activity occurred                                                            |                                                   |
| app_id             | Redfast app id                                                                              | Optional                                          |
| traits             | Key value pairs of user attributes that have been ingested from external and in-app sources | Optional                                          |
| segments           | List of segment names with ids at the time the event occurred                               | Optional                                          |
| paths              | List of personalization names user was eligible for at the time the event occurred          | Optional                                          |

### Event Types

| Type                         | Description                                                                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Impression                   | User was shown the prompt                                                                                                      |
| Timeout                      | User did not respond before the prompt timer ran out                                                                           |
| Dismiss                      | User dismissed the prompt by clicking on the `X` or outside the window (as configured in the Redfast Console)                  |
| Decline                      | User clicked on the decline link                                                                                               |
| Click                        | User accepted the prompt (this has been phased out in favor of Goal)                                                           |
| Goal                         | User accepted the prompt                                                                                                       |
| Custom_Goals_[Activity Type] | User completed the defined custom goal after previously performing the specified activity type on a prompt                     |
| Exclude                      | User is part of the holdout group or not eligible for a prompt after the specified User Limit has been exceeded.               |
| Holdout                      | User is part of the holdout group or not eligible for a prompt after the specified User Limit has been exceeded.               |
| Pipeline_Impression          | User was shown the prompt and is a member of a pipeline stage                                                                  |
| Pipeline_Transition          | User is transitioned from one pipeline stage to another - see `Pipeline_Stage_Start_Name` and `Pipeline_Stage_End_Name` fields |

# Custom Web API Firehose

This option provides near realtime data. Redfast can send single or batched events within sub-minute windows to an endpoint of your choice. Please provide the following data to Redfast.

- URL
- API Key, Access Tokens, etc
- Request type (GET, POST, PUT)

### Payload format

The payload will appear as a list of objects. In the case of S3 each event will appear as one object per row.

```json
[
  {
  "app_id":"74f72649-0327-4911-bd21-a4cd533cec1c",
  "user_id":"123",
  "anonymous_user_id":"2528a84d8fa8151331e711491d208dd37da70f862929627683e3a58250c8a020",
  "event":"Home Page",
  "platform":"redfast",
  "type":"page",
  "ts":1630476856,
  "properties":{
      "id":"8e282c72-07da-4c2f-bf91-85df633828af",
      "values":[
          {
          "url_hash":"",
          "url_path":"/",
          "query_params":""
          }
      ],
      "options":{
          "use_regex":false
      }
  },
  "traits":{
      "subscription_end_date":"20210825",
      "subscription_active":false,
      "trial":true,
      "city":"Los Angeles",
      "continent":"North America",
      "country":"US",
      "metro_code":"323",
      "postal":"90028",
      "subdiv":"California",
      "time_zone":"America/Los_Angeles"
  },
  "segments":[
      {
          "id":"b7ca7eca-802d-40f0-94ed-c1dc7cd03ab0",
          "name":"Engaged"
      },
      {
          "id":"d9b3c90c-2aed-4a10-b9d4-64b638aba5af",
          "name":"All Users"
      },
      {
          "id":"7106f30f-1696-44de-a2aa-8bd245ba10fa",
          "name":"Trial"
      }
  ]
  },
  {
      "app_id":"74f72649-0327-4911-bd21-a4cd533cec1c",
      "user_id":"123",
      "anonymous_user_id":"2528a84d8fa8151331e711491d208dd37da70f862929627683e3a58250c8a020",
      "event":"Click Purchase",
      "platform":"redfast",
      "type":"track",
      "properties":{
          "values":[
              "#purchase-tab"
          ],
          "id":"566729e8-4499-4baf-96a8-29a99b96a3f8",
          "options":{
              "use_regex":false
          }
      },
      "ts":1630492511,
      "traits":{
          "email":"julian@redfast.com",
          "subscription_end_date":"20210825",
          "subscription_active":false,
          "trial":true,
          "city":"Los Angeles",
          "continent":"North America",
          "country":"US",
          "metro_code":"323",
          "postal":"90028",
          "subdiv":"California",
          "time_zone":"America/Los_Angeles"
      },
      "segments":[
          {
              "id":"b7ca7eca-802d-40f0-94ed-c1dc7cd03ab0",
              "name":"Engaged"
          },
          {
              "id":"d9b3c90c-2aed-4a10-b9d4-64b638aba5af",
              "name":"All Users"
          },
          {
              "id":"7106f30f-1696-44de-a2aa-8bd245ba10fa",
              "name":"Trial"
          }
      ],
      "paths":[
          {
              "id":"3e6af999-9337-43d2-baa7-fefb0f062b2d",
              "name":"1-1 Trainer Prompt",
              "device_type":"web",
              "zone":"recommended-trainer"
          },
          {
              "id":"2b0e6e0f-8012-4711-acc8-868f71fbdf61",
              "name":"$10 off - Generic Users",
              "device_type":"web",
              "zone":"vip-special"
          },
          {
              "id":"87190eda-62ab-4d18-87b1-926302dc6083",
              "name":"Fall Apparel Prompt",
              "device_type":"web",
              "zone":null
          }
      ]
  },
  {
      "app_id":"74f72649-0327-4911-bd21-a4cd533cec1c",
      "user_id":"123",
      "anonymous_user_id":"2528a84d8fa8151331e711491d208dd37da70f862929627683e3a58250c8a020",
      "event":"Click Purchase",
      "platform":"redfast",
      "type":"custom",
      "properties":{
          "id":"566729e8-4499-4baf-96a8-29a99b96a3f8"
      },
      "ts":1630502588,
      "traits":{
          "email":"julian@redfast.com",
          "subscription_end_date":"20210825",
          "subscription_active":false,
          "trial":true,
          "city":"Los Angeles",
          "continent":"North America",
          "country":"US",
          "metro_code":"323",
          "postal":"90028",
          "subdiv":"California",
          "time_zone":"America/Los_Angeles"
      },
      "segments":[
          {
              "id":"b7ca7eca-802d-40f0-94ed-c1dc7cd03ab0",
              "name":"Engaged"
          },
          {
              "id":"d9b3c90c-2aed-4a10-b9d4-64b638aba5af",
              "name":"All Users"
          },
          {
              "id":"7106f30f-1696-44de-a2aa-8bd245ba10fa",
              "name":"Trial"
          }
      ],
      "paths":[
          {
              "id":"3e6af999-9337-43d2-baa7-fefb0f062b2d",
              "name":"1-1 Trainer Prompt",
              "device_type":"web",
              "zone":"recommended-trainer"
          },
          {
              "id":"2b0e6e0f-8012-4711-acc8-868f71fbdf61",
              "name":"$10 off - Generic Users",
              "device_type":"web",
              "zone":"vip-special"
          },
          {
              "id":"87190eda-62ab-4d18-87b1-926302dc6083",
              "name":"Fall Apparel Prompt",
              "device_type":"web",
              "zone":null
          }
      ]
  }
]
```

## API Data Specifications

All data is JSON formatted with the following fields:

| Field              | Description                                                                                 | Notes                                             |
| ------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| app_id             | Redfast app id                                                                              |                                                   |
| user_id            | Primary user identifier                                                                     |                                                   |
| anonymous_user_id  | Identifier for a user in the event userId is not available                                  |                                                   |
| event              | Name of event                                                                               | Name of event being exported                      |
| platform           | Type of integration                                                                         | Always redfast for usage                          |
| type               | Type of tracker                                                                             | Types: page, track, custom                        |
| properties.id      | Usage Tracker id                                                                            |                                                   |
| properties.values  | Configured in Redfast Console                                                               |                                                   |
| properties.options | Additional options                                                                          | Specifies if Regex is used for page type trackers |
| ts                 | Timestamp that activity occurred                                                            |                                                   |
| traits             | Key value pairs of user attributes that have been ingested from external and in-app sources |                                                   |
| segments           | List of segment names with ids at the time the event occurred                               |                                                   |
| paths              | List of personalization names user was eligible for at the time the event occurred          |                                                   |

### Usage Types

| Type   | Description                                                                                                      |
| ------ | ---------------------------------------------------------------------------------------------------------------- |
| page   | Tracker on a specific page e.g. website.com/profile                                                              |
| track  | Button or CSS class e.g.    .purchase                                                                            |
| custom | Device Screen (ViewController) or any arbritary tracker specified in an external system e.g. trasaction complete |

### API push

Data will be pushed to your ingest endpoint in the following format. The data will always come in the form of a list/array of objects. Each object represents an event with metadata using the payload format above.

```
curl 'example.backendurl.com/v1/api/ingest/' \
  -X 'POST' \
  -H 'content-type: application/json' \
  -H 'your-api-key: abcdef' \
  --data-raw '[
  {
  "app_id":"74f72649-0327-4911-bd21-a4cd533cec1c",
  "user_id":"123",
  "anonymous_user_id":"2528a84d8fa8151331e711491d208dd37da70f862929627683e3a58250c8a020",
  "event":"Home Page",
  "platform":"redfast",
  "type":"page",
  "ts":1630476856,
  "properties":{
      "id":"8e282c72-07da-4c2f-bf91-85df633828af",
      "values":[
          {
          "url_hash":"",
          "url_path":"/",
          "query_params":""
          }
      ],
      "options":{
          "use_regex":false
      }
  },
  "traits":{
      "subscription_end_date":"20210825",
      "subscription_active":false,
      "trial":true,
      "city":"Los Angeles",
      "continent":"North America",
      "country":"US",
      "metro_code":"323",
      "postal":"90028",
      "subdiv":"California",
      "time_zone":"America/Los_Angeles"
  },
  "segments":[
      {
          "id":"b7ca7eca-802d-40f0-94ed-c1dc7cd03ab0",
          "name":"Engaged"
      },
      {
          "id":"d9b3c90c-2aed-4a10-b9d4-64b638aba5af",
          "name":"All Users"
      },
      {
          "id":"7106f30f-1696-44de-a2aa-8bd245ba10fa",
          "name":"Trial"
      }
  ],
  "paths":[
        {
            "id":"3e6af999-9337-43d2-baa7-fefb0f062b2d",
            "name":"1-1 Trainer Prompt",
            "device_type":"web",
            "zone":"recommended-trainer"
        },
        {
            "id":"2b0e6e0f-8012-4711-acc8-868f71fbdf61",
            "name":"$10 off - Generic Users",
            "device_type":"web",
            "zone":"vip-special"
        },
        {
            "id":"87190eda-62ab-4d18-87b1-926302dc6083",
            "name":"Fall Apparel Prompt",
            "device_type":"web",
            "zone":null
        }
    ]
}]' \
  --compressed
```