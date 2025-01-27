---
title: Invisible
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
This unique prompt is used to activate or deactivate particular behaviors on your application without a user interaction. A hidden action that is performed on a particular page or when a particular event is fired. 

<Image align="center" className="border" border={true} src="https://files.readme.io/c386e48-image.png" />

Example use cases include hiding ads, automatically adding a show to a user’s watchlist, providing a discount or triggering an API.

The configuration is very similar to a [popup](overlays#how-to-video) with the following differences:

* There is no UI associated with this prompt.
* All server-side and client-side actions will automatically execute upon trigger.

## Add Metadata

Metadata tags may be added to provide additional context or ability to implement custom behavior not handled by preconfigured server-side and client-side actions. These tags are accessible via the Redfast SDK and can be used to adjust the user experience or enable/disable features.

* [ ] Click the Edit (pencil) icon to open the Metadata modal.

  ![](https://files.readme.io/e45aa27-image.png)
* [ ] Add one or more key-value pairs

  ![](https://files.readme.io/7db1c7e-image.png)
* [ ] Retrieve Metadata

```
Redfast.getMetas()

  {'meta1': 'val1', 'meta2': 'val2'}
```

## Test the prompt

A prompt can be tested before it is published to all users. These tests are useful for refining triggers, creative, schedules, and actions. You can learn to do so by following the [test user guide](test-users).

<br />