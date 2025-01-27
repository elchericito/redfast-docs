---
title: Localization (Multi Language Support)
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
This article describes how to localize a single prompt to the language specified by the user’s browser or app’s locale settings without creating multiple prompts (one for each language).

## Setup

Typically each prompt contains a headline, message body, and call to action buttons. Redfast prompt localization process will require you to provide translations for each of these elements in each of the desired languages. This is accomplished via a CSV that is uploaded to Pulse. Each row in the CSV should correspond to a [ISO 639-1 2-letter or 4-letter language code](https://www.w3schools.com/tags/ref_language_codes.asp). The columns correspond to specific text fields within the prompt. Use the [sample csv](https://assets.redfast.com/docs/translations_sample.csv), and the graphics below, as a guide.

Desktop:

<Image align="center" className="border" border={true} src="https://files.readme.io/dc57b6a-image.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/18bf885-image.png" />

Devices:

<Image align="center" className="border" border={true} src="https://files.readme.io/1facf58-image.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/a2ca771-image.png" />

<br />

> 🚧 Do not delete columns in the CSV. All columns are required.
>
> Leave the fields you do not intend to use blank.

<br />

Exactly **one** (1) language should have `default` set to `true`. The values in this row will be returned as the default for end users whose detected language does not appear in the list.

After uploading the CSV and saving the prompt, the language selector dropdown will appear in the prompt preview area. Select a language to view the preview in Pulse. Click Live Preview to view the preview within your site.

<Image align="center" className="border" border={true} src="https://files.readme.io/ecfc764-image.png" />

## Technical Information

Redfast detects the end user’s language from three sources:

1. The return value of the `setLanguage()` function within the custom web snippet (highest priority)
2. The `language` trait associated with the end user
3. The `Accept-Language` HTTP header (lowest priority)

Redfast will first attempt to find an exact match against the end user’s detected language. If no exact match is found, Redfast may attempt to find a more generic match. For example, if the end user’s language is EN-US, Redfast will first try to find EN-US, and then EN. In this example, EN-GB WOULD NOT be matched to this user. If no matching 4-letter or 2-letter languages are available, Redfast will return the default language, as specified in the CSV.