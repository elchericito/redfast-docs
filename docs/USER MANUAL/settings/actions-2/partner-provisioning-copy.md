---
title: Partner APIs
deprecated: false
hidden: true
metadata:
  robots: index
---
# Introduction

The Partner APIs allows for the creation and modification of Redfast prompts via server-side integration with partners.

## Endpoint Info

**Base URL**: `https://<subdomain>.redfast.com`

<br />

# Get Prompts by Tag Name

<br />

This API should be invoked to retrieve a list of prompts based on tag name.

<br />

## Endpoint

**GET /v1/apps/\<app\_id>/paths?tag\_name=involuntary\_churn**

<br />

## Headers

* **Content-Type**: `application/json`
* **Authorization**: Bearer \<jwt\_token>

## Query Params

The request should include the following query params:

* **tag\_name**: (optional) Get prompts by tag\_name
  <br />

## Response

<br />

```json json
[
 {
  "id": "c6e948dd-06ec-4d10-acc9-a6b4ba2823ff",
  "slug": "c6e948dd-06ec-4d10-acc9-a6b4ba2823ff",
  "name": "Sample Prompt",
  "description": null,
  "device_type": "web",
  "path_type": "retention_modal",
  "start_date": "2025-02-18T00:00:00.000Z",
  "end_date": "2026-02-18T23:59:59.000Z",
  "is_enabled": false,
  "is_expired": false,
  "path_group_id": "54ca9f57-f764-4595-b8bc-f7df5fb1905f",
  "filter": {
    "schedule": [],
    "traffic": {
      "limit": 0,
      "is_limited": false
    },
    "supply": {
      "budget": 0,
      "budget_decrementer": 1,
      "is_budgeted": false,
      "availability": null,
      "support_agents": null
    },
    "frequency_cap": {
      "cap": 60,
      "cap_seconds": 2592000,
      "is_capped": false
    },
    "sequence_options": {
      "skip_filter": {
        "interaction_types": []
      },
      "exclusion_filter": {
        "interaction_types": [
          "accepted"
        ]
      },
      "continue_filter": {
        "interaction_types": [],
        "order": 0,
        "interval_minutes": 0
      }
    },
    "users": {
      "limit": 0,
      "is_limited": false
    },
    "deliveries": {
      "limit": 0,
      "is_limited": false
    },
    "is_translated": false,
    "connectors": {
      "pinpoint": {
        "campaign_id": null
      },
      "settings": {
        "synchronous": false
      }
    }
  },
  "actions": {
    "rf_retention_title": "Movies without limits",
    "rf_retention_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
    "rf_retention_acceptance_text": "Thank You",
    "rf_retention_button1_text": "Accept",
    "rf_retention_button3_text": "No thanks",
    "rf_retention_button2_text": "",
    "rf_settings_close_seconds": "30",
    "rf_settings_fill_color": "#FFFFFF",
    "button1_bg_color": "#3096ED",
    "button2_bg_color": "",
    "rf_settings_close_button_enabled": "true",
    "rf_settings_cancel_button_enabled": "true",
    "rf_settings_custom_goal_expire_hours": "48",
    "rf_settings_decline_interval": "INF",
    "rf_settings_dismiss_interval": "1440",
    "rf_settings_timeout_interval": "1440",
    "rf_settings_accept_interval": "INF",
    "rf_settings_window_max_width": "1100px",
    "rf_settings_pop_up_size": "medium",
    "rf_settings_overlay_background": "#252323B3",
    "rf_settings_bg_image": "https://assets.redfastlabs.com/videos/cover.jpg",
    "rf_settings_text_container_max_width": "",
    "rf_settings_title_font_size": "60px",
    "rf_settings_message_font_size": "18px",
    "rf_settings_bg_image_color": "#999999",
    "rf_settings_title_padding_top": "240px",
    "rf_settings_mobile_title_font_size": "30px",
    "rf_settings_mobile_message_font_size": "16px",
    "rf_settings_mobile_title_padding_top": "180px",
    "rf_settings_timer_font_size": "14px",
    "rf_settings_timer_font_color": "#FFFFFF",
    "rf_settings_mobile_bg_image": "https://assets.redfastlabs.com/videos/mweb_video_bg.jpg",
    "rf_settings_close_seconds_text": "seconds remaining",
    "rf_settings_custom_css": "",
    "rf_settings_video_height": "619px",
    "rf_settings_video_width": "1100px",
    "rf_settings_video_poster": "https://assets.redfastlabs.com/videos/cover.jpg",
    "rf_settings_video_src": "https://assets.redfastlabs.com/videos/sample_6.mp4",
    "rf_settings_video_media_type": "mp4",
    "rf_settings_video_muted": "true",
    "rf_settings_video_loop": "true",
    "rf_settings_video_controls": "false",
    "rf_settings_video_is_url": "false",
    "rf_settings_deeplink": "",
    "button1_text_color": "#FFFFFF",
    "button1_highlight_color": "#FFFF00",
    "button3_text_color": "#FFFFFF",
    "button3_highlight_color": "#FFFF00",
    "rf_retention_button2_text_color": "#FFFFFF",
    "button2_highlight_color": "#FFFF00",
    "rf_metadata": "",
    "rf_mobile_title": "Movies without limits",
    "rf_mobile_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
    "rf_retention_align": "left",
    "rf_retention_img_align": "right",
    "rf_email_button_radius": "0px",
    "rf_retention_survey_selected": "false",
    "rf_retention_survey_options_total": "3",
    "rf_retention_survey_options_font_size": "20px",
    "rf_retention_survey_option_1_label": "Option 1",
    "rf_retention_survey_option_2_label": "Option 2",
    "rf_retention_survey_option_3_label": "Option 3",
    "rf_retention_survey_option_4_label": "Option 4",
    "rf_retention_survey_option_5_label": "Option 5",
    "rf_retention_survey_option_1_value": "opt1",
    "rf_retention_survey_option_2_value": "opt2",
    "rf_retention_survey_option_3_value": "opt3",
    "rf_retention_survey_option_4_value": "opt4",
    "rf_retention_survey_option_5_value": "opt5",
    "countdown_caption": "Offer ends in",
    "countdown_end_datetime": "",
    "countdown_size": "large",
    "countdown_position": "top",
    "countdown_enabled": "false",
    "rf_settings_video_autoplayed": "false",
    "rf_retention_button_border_color": "",
    "rf_mobile_border-top-right-radius": "0px",
    "rf_mobile_border-top-left-radius": "0px",
    "rf_mobile_border-bottom-left-radius": "0px",
    "rf_mobile_border-bottom-right-radius": "0px",
    "rf_retention_border-top-right-radius": "0px",
    "rf_retention_border-top-left-radius": "0px",
    "rf_retention_border-bottom-left-radius": "0px",
    "rf_retention_border-bottom-right-radius": "0px",
    "rf_mobile_border-width": "0px",
    "rf_retention_border-width": "0px",
    "rf_mobile_border-style": "solid",
    "rf_retention_border-style": "solid",
    "rf_mobile_border-color": "#000000",
    "rf_retention_border-color": "#000000",
    "rf_mobile_box-sizing": "false",
    "rf_retention_box-sizing": "false",
    "rf_mobile_box-shadow": "0px 0px 0px 0px #000000",
    "rf_retention_box-shadow": "0px 0px 0px 0px #000000",
    "rf_settings_custom_goal_interval": "INF",
    "rf_settings_mobile_video_src": "https://assets.redfastlabs.com/videos/sample_6.mp4",
    "rf_settings_mobile_video_is_url": "false",
    "rf_settings_mobile_video_muted": "true",
    "rf_settings_mobile_video_loop": "true",
    "rf_settings_mobile_video_autoplayed": "false",
    "rf_settings_mobile_video_media_type": "mp4",
    "rf_settings_mobile_video_poster": "https://assets.redfastlabs.com/videos/cover.jpg",
    "consent_enabled": "false",
    "consent_prechecked": "false",
    "consent_text": "Enter your legal text here",
    "consent_font_size": "18px",
    "consent_font_color": "#FFFFFF",
    "rf_settings_bg_image_ios_ipad_preview_composite": "",
    "rf_settings_bg_image_ios_ipad_composite": "",
    "rf_settings_bg_image_ios_iphone_composite": "",
    "rf_settings_bg_image_ios_iphone_2x_composite": "",
    "rf_settings_custom_css_scoped": ""
  },
  "custom_devices": [],
  "data": {
    "goals": {
      "tz_offset": -7,
      "last_seven_days": {
        "name": "Last 7 days",
        "data": [
          {
            "date": "20250401",
            "count": 0
          },
          {
            "date": "20250402",
            "count": 0
          },
          {
            "date": "20250403",
            "count": 0
          },
          {
            "date": "20250404",
            "count": 0
          },
          {
            "date": "20250405",
            "count": 0
          },
          {
            "date": "20250406",
            "count": 0
          },
          {
            "date": "20250407",
            "count": 0
          }
        ],
        "uniques": 0
      }
    },
    "uimpressions": {
      "tz_offset": -7,
      "last_seven_days": {
        "name": "Last 7 days",
        "data": [
          {
            "date": "20250401",
            "count": 0
          },
          {
            "date": "20250402",
            "count": 0
          },
          {
            "date": "20250403",
            "count": 0
          },
          {
            "date": "20250404",
            "count": 0
          },
          {
            "date": "20250405",
            "count": 0
          },
          {
            "date": "20250406",
            "count": 0
          },
          {
            "date": "20250407",
            "count": 0
          }
        ],
        "uniques": 0
      }
    },
    "impressions": {
      "tz_offset": -7,
      "last_seven_days": {
        "name": "Last 7 days",
        "data": [
          {
            "date": "20250401",
            "count": 0
          },
          {
            "date": "20250402",
            "count": 0
          },
          {
            "date": "20250403",
            "count": 0
          },
          {
            "date": "20250404",
            "count": 0
          },
          {
            "date": "20250405",
            "count": 0
          },
          {
            "date": "20250406",
            "count": 0
          },
          {
            "date": "20250407",
            "count": 0
          }
        ],
        "uniques": 0
      }
    }
  },
  "creator": {
    "id": "7a3347c6-9a9d-4a10-aa0d-9f8206467c49",
    "name": "J L",
    "email": "jlo@redfast.com",
    "is_redfast": true
  },
  "sequence_id": null,
  "custom_filter": {},
  "curr_limit": 0,
  "curr_deliveries": 0,
  "curr_users": 0,
  "curr_budget": 0,
  "sequence": {},
  "pipeline": {},
  "segments": [],
  "tags": [
    {
      "id": "49efbd0d-8710-4948-8fc0-fe3a2e10a084",
      "title": "descr",
      "color": "#FFDDEF"
    }
  ],
  "experiment": null
}
]
```

<br />

<br />

# Update Prompt

This API should be invoked to update an existing prompt. Omitted attributes will be ignored.

## Endpoint

**PUT /v1/apps/\<app\_id>/paths/\<path\_id>**

## Headers

* **Content-Type**: `application/json`
* \*\*Authorization\*\*: Bearer \<jwt\_token>

<br />

## Body

The request body should be a JSON including the following properties. All fields are optional except for actions:

* **id**: (required) Prompt id
* **name**: Prompt name
* **description**: Prompt description
* **start\_date**: Start date
* **end\_date**: Start date
* **is\_enabled**: Enable prompt
* **actions**: Prompt attributes. All attributes are strings.

## Response

```json json
{
  "id": "c6e948dd-06ec-4d10-acc9-a6b4ba2823ff",
  "slug": "c6e948dd-06ec-4d10-acc9-a6b4ba2823ff",
  "name": "Sample Prompt",
  "description": null,
  "device_type": "web",
  "path_type": "retention_modal",
  "start_date": "2025-02-18T00:00:00.000Z",
  "end_date": "2026-02-18T23:59:59.000Z",
  "is_enabled": false,
  "is_expired": false,
  "path_group_id": "54ca9f57-f764-4595-b8bc-f7df5fb1905f",
  "actions": {
    "rf_retention_title": "Movies without limits",
    "rf_retention_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
    "rf_retention_acceptance_text": "Thank You",
    "rf_retention_button1_text": "Accept",
    "rf_retention_button3_text": "No thanks",
    "rf_retention_button2_text": "",
    "rf_settings_close_seconds": "30",
    "rf_settings_fill_color": "#FFFFFF",
    "button1_bg_color": "#3096ED",
    "button2_bg_color": "",
    "rf_settings_close_button_enabled": "true",
    "rf_settings_cancel_button_enabled": "true",
    "rf_settings_custom_goal_expire_hours": "48",
    "rf_settings_decline_interval": "INF",
    "rf_settings_dismiss_interval": "1440",
    "rf_settings_timeout_interval": "1440",
    "rf_settings_accept_interval": "INF",
    "rf_settings_window_max_width": "1100px",
    "rf_settings_pop_up_size": "medium",
    "rf_settings_overlay_background": "#252323B3",
    "rf_settings_bg_image": "https://assets.redfastlabs.com/videos/cover.jpg",
    "rf_settings_text_container_max_width": "",
    "rf_settings_title_font_size": "60px",
    "rf_settings_message_font_size": "18px",
    "rf_settings_bg_image_color": "#999999",
    "rf_settings_title_padding_top": "240px",
    "rf_settings_mobile_title_font_size": "30px",
    "rf_settings_mobile_message_font_size": "16px",
    "rf_settings_mobile_title_padding_top": "180px",
    "rf_settings_timer_font_size": "14px",
    "rf_settings_timer_font_color": "#FFFFFF",
    "rf_settings_mobile_bg_image": "https://assets.redfastlabs.com/videos/mweb_video_bg.jpg",
    "rf_settings_close_seconds_text": "seconds remaining",
    "rf_settings_custom_css": "",
    "rf_settings_video_height": "619px",
    "rf_settings_video_width": "1100px",
    "rf_settings_video_poster": "https://assets.redfastlabs.com/videos/cover.jpg",
    "rf_settings_video_src": "https://assets.redfastlabs.com/videos/sample_6.mp4",
    "rf_settings_video_media_type": "mp4",
    "rf_settings_video_muted": "true",
    "rf_settings_video_loop": "true",
    "rf_settings_video_controls": "false",
    "rf_settings_video_is_url": "false",
    "rf_settings_deeplink": "",
    "button1_text_color": "#FFFFFF",
    "button1_highlight_color": "#FFFF00",
    "button3_text_color": "#FFFFFF",
    "button3_highlight_color": "#FFFF00",
    "rf_retention_button2_text_color": "#FFFFFF",
    "button2_highlight_color": "#FFFF00",
    "rf_metadata": "",
    "rf_mobile_title": "Movies without limits",
    "rf_mobile_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
    "rf_retention_align": "left",
    "rf_retention_img_align": "right",
    "rf_email_button_radius": "0px",
    "rf_retention_survey_selected": "false",
    "rf_retention_survey_options_total": "3",
    "rf_retention_survey_options_font_size": "20px",
    "rf_retention_survey_option_1_label": "Option 1",
    "rf_retention_survey_option_2_label": "Option 2",
    "rf_retention_survey_option_3_label": "Option 3",
    "rf_retention_survey_option_4_label": "Option 4",
    "rf_retention_survey_option_5_label": "Option 5",
    "rf_retention_survey_option_1_value": "opt1",
    "rf_retention_survey_option_2_value": "opt2",
    "rf_retention_survey_option_3_value": "opt3",
    "rf_retention_survey_option_4_value": "opt4",
    "rf_retention_survey_option_5_value": "opt5",
    "countdown_caption": "Offer ends in",
    "countdown_end_datetime": "",
    "countdown_size": "large",
    "countdown_position": "top",
    "countdown_enabled": "false",
    "rf_settings_video_autoplayed": "false",
    "rf_retention_button_border_color": "",
    "rf_mobile_border-top-right-radius": "0px",
    "rf_mobile_border-top-left-radius": "0px",
    "rf_mobile_border-bottom-left-radius": "0px",
    "rf_mobile_border-bottom-right-radius": "0px",
    "rf_retention_border-top-right-radius": "0px",
    "rf_retention_border-top-left-radius": "0px",
    "rf_retention_border-bottom-left-radius": "0px",
    "rf_retention_border-bottom-right-radius": "0px",
    "rf_mobile_border-width": "0px",
    "rf_retention_border-width": "0px",
    "rf_mobile_border-style": "solid",
    "rf_retention_border-style": "solid",
    "rf_mobile_border-color": "#000000",
    "rf_retention_border-color": "#000000",
    "rf_mobile_box-sizing": "false",
    "rf_retention_box-sizing": "false",
    "rf_mobile_box-shadow": "0px 0px 0px 0px #000000",
    "rf_retention_box-shadow": "0px 0px 0px 0px #000000",
    "rf_settings_custom_goal_interval": "INF",
    "rf_settings_mobile_video_src": "https://assets.redfastlabs.com/videos/sample_6.mp4",
    "rf_settings_mobile_video_is_url": "false",
    "rf_settings_mobile_video_muted": "true",
    "rf_settings_mobile_video_loop": "true",
    "rf_settings_mobile_video_autoplayed": "false",
    "rf_settings_mobile_video_media_type": "mp4",
    "rf_settings_mobile_video_poster": "https://assets.redfastlabs.com/videos/cover.jpg",
    "consent_enabled": "false",
    "consent_prechecked": "false",
    "consent_text": "Enter your legal text here",
    "consent_font_size": "18px",
    "consent_font_color": "#FFFFFF",
    "rf_settings_bg_image_ios_ipad_preview_composite": "",
    "rf_settings_bg_image_ios_ipad_composite": "",
    "rf_settings_bg_image_ios_iphone_composite": "",
    "rf_settings_bg_image_ios_iphone_2x_composite": "",
    "rf_settings_custom_css_scoped": ""
  }
}
```

<br />

# Testing

<br />

Authentication utilizes a shared secret (both Test and Production secrets will be provided). When utilizing the Test secret, a valid API response is returned but a new tenant will not be provisioned.

<br />

# Error Responses

<br />

Redfast uses conventional HTTP response codes indicating success or failure of an API request. Codes in the 2xx range indicate success while codes in the 4xx or 5xx ranges indicate an error.

<br />

* 200 OK - Normal response
* 401 Unauthorized - Shared secret is incorrect

<br />

```
{
  "success": false,
  "status": "invalid_token"
}
```

<br />

* 404 Not Found - Requested resource was not found

<br />

```
{
  "success": false,
  "status": "not_found",
  "message": "resource not found"
}
```

<br />

<br />

* 422 Unprocessable Entity - Invalid or missing information

<br />

```
{
  "success": false,
  "status": "missing_or_invalid_info",
  "message": "id missing"
}
```

<br />

* 5xx - Something went wrong with the Redfast endpoint (rare)