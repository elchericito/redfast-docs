---
title: Data sources
excerpt: Use content from external sources within dynamic variables
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Any user information synced to Redfast can be used not only for segmentation but also as dynamic content within a prompt's title or message body using [Dynamic Variables](doc:dynamic-variables). 

Data source variables are another way add expand the content that can be shown. By uploading a CSV, you can import structured content to use within prompts.

For example, say you want to tell the user "Get 1 month off" but the actual discount maybe varied by the marketing department based on time of year so it is "Get 2 weeks off" One way is to manually edit the prompt each time there is a change but a better way is to use a coupon data source.

In this example, you can upload a csv with various coupon attributes.

<Image align="center" src="https://files.readme.io/6a1c972-Capture-2024-05-20-182307.png" />

and reference just the value in the prompt by inserting dynamic content. This eliminated errors and allows you to import structured data from external sources into the system.

<Image align="center" src="https://files.readme.io/cbfa10c-Capture-2024-05-20-182358.png" />
