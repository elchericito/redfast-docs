---
title: Accessibility
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
Redfast monitors the Web Content Accessibility Guidelines (WCAG), which outline a set of guidelines to provide greater accessibility to the components rendered by the platform. The following describes the steps taken to comply with relevant guidelines. Please reach out to your account manager if you have questions pertaining to how to best configure Redfast prompts within your existing WCAG compliant web site.

## Perceivable

### 1.1 Text Alternatives

All text configured for a prompt is rendered without further modification and not composited as an image. This ensures compatibility with screen readers. Images utilized within a prompt are used in the background for styling purposes. A text alternative may be specified for the background image if needed.

### 1.2 Time-based Media

Not applicable.

### 1.3 Adaptable

Not applicable for common use cases.

### 1.4 Distinguishable

When configuring a prompt, Redfast provides the designer the flexibility to address these set of guidelines.

## Operable

### 2.1 Keyboard Accessible

Keyboard controls work as intended across all prompt types. Buttons rendered by the Redfast SDK support keyboard-based focus and click actions. For non-standard elements that accept a click, the designer may make custom HTML/CSS modifications to comply with guidelines.

### 2.2 Enough Time

Prompts can be configured with a design and a specified amount of time the content is available to comply with this set of guidelines.

### 2.3 Seizures

By default, prompts do not contain any flashing that may induce this medical condition.

### 2.4 Navigable

Redfast prompts are generally utilized to introduce smaller pieces of content within an existing web page, and most of these guidelines apply to the existing web page containing all of the content and do not apply to Redfast directly. To the extent these guidelines call for navigation of Redfast elements within the context of the entire web page, Redfast can be configured with a design for compliance..

## Understandable

### 3.1 Readable

Redfast provides a configuration console from which designers have full editorial control over the language and text content of the prompt.

### 3.2 Predictable

Within a Redfast prompt, focus events operate without an unintended change of context. Guidelines about Input and Consistent Navigation generally apply to the entire web page, and not the Redfast prompt specifically. To the extent needed, Redfast prompts can be configured within the console to fit within the guidelines required by the parent web page.

### 3.3 Input Assistance

If applicable, Redfast provides error messages if input is invalid/does not pass validation. Error messages are removed once input has been corrected.

## Robust

### 4.1 Compatible

Redfast complies with modern web standards and utilizes standard HTML elements per best practice guidelines. Per the specification, rendered HTML will be nested and have complete start and end tags. Note that designers must ensure compliance if utilizing custom HTML/CSS in the configuration of a prompt.
