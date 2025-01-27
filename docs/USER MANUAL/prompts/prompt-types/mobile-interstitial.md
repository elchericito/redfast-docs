---
title: Mobile Interstitial
excerpt: Full screen prompt for iOS and Android phones
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 📘 Note: This prompt type is scheduled to be released in 2024 Q4. Reach out to your customer success manager for more details.

## Summary

Redfast supports the creation and delivery of a full screen prompt for use on mobile devices such as iPhones and Android phones.

<block:image>
  {`
    "images": [
      {
        "image": [
          "https://files.readme.io/fb9833de82d86aafb60d172d84d67b7c7b2d7d361dbecf2bd8419825736f7e54-Screenshot_2024-10-01_at_3.36.35_PM.png",
          "",
          ""
        ],
        "align": "center"
      }
    ]
  `}
</block:image>

## UI Elements

Using the Redfast admin console (Pulse), you may specify various elements and interactions for this prompt style. The background image, title, and message body are rendered into a composite image used by the device SDK while the buttons are native elements rendered by the device SDK.

The following elements of the prompt may be configured:

| Item             | Type      | Description                                             |
| :--------------- | :-------- | :------------------------------------------------------ |
| Title            | Text      | Headline text                                           |
| Message          | Text      | Message body                                            |
| Background color | Hex color | Solid color                                             |
| Background Image | Image     | Image to be used as background                          |
| Legal text       | Text      | Legal disclaimer text                                   |
| Close button     | Radio     | Allow close or not                                      |
| Close timer      | Text      | Countdown timer in seconds                              |
| **Buttons**      |           | Up to three buttons                                     |
| Text             | Text      | Button text                                             |
| Text color       | Hex color | Button text color                                       |
| Background color | Hex color | Button background color - Hex code with alpha (8 chars) |
| Font family      | Dropdown  | iOS: standard fonts; Android: font family name          |
| Border radius    | String    | Border radius (px)                                      |
| Border color     | Hex color | Button border color - Hex code with alpha (8 chars)     |
| Border thickness | Number    | Thickness (px)                                          |
| In App           | Text      | IAP Product/SKU Code                                    |
| Deep Link        | Link      | Deep link URL                                           |
|                  |           |                                                         |

## Triggers

As with any native device prompt, your app must decide when the prompt will be shown by specifying screen name and/or element clickID. Please refer to the Redfast [iOS](ios-sdk) and [Android SDK](android-sdk) docs for additional information.