---
title: Can I use a custom font in my prompts?
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
Sure, you can apply your custom font to any of your prompt elements using the Custom CSS section of the Editor.\
Refer to this [article](styling-fine-tuning-css-selectors) for a list of CSS style classes that may be used to modify the default styling of any Redfast prompt.

<Image align="center" className="border" border={true} src="https://files.readme.io/396ca85-image.png" />

```
.rfmodal-content-wrapper {
  font-family: "Roboto", sans-serif!important;
}
```

> 📘 Make sure to only use the fonts that load on your website.

> 🚧 Custom fonts won't display in the Editor, but you will see them loaded when using the 'Live preview' button and when the prompt is live as long as the custom fonts you set are loaded on your website.
