---
title: Styling/ Fine tuning (CSS selectors)
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
# Prompt Styling

## Quick Reference

The following CSS style classes may be used to modify the default styling of any Redfast prompt.

| Item                       | Description                  |
| -------------------------- | ---------------------------- |
| .rfmodal-content-wrapper   | prompt area                  |
| .rfmodal-inner-wrapper     | prompt text content area     |
| .rfmodal-backgroundimage   | prompt background image      |
| .rfmodal-header            | prompt title                 |
| .rfmodal-header-mobileweb  | prompt title (mobile)        |
| .rfmodal-message           | prompt message body          |
| .rfmodal-message-mobileweb | prompt message body (mobile) |
| .rfmodal-button-yes        | primary accept button        |
| .rfmodal-button-no         | secondary button             |
| .rfmodal-footer            | button area                  |
| .rfmodal-close             | dismiss button               |
| .rfmodal-close-icon        | dismiss button icon          |
| .rf-radio-group            | survey form options          |
| .rf-radio-item             | survey form line item        |

## Full Reference

### Desktop | (Video(web), retention\_modal(web), ios, android\_os, tv\_os,roku\_os)

* .rfmodal-content.outer-modal - **modal**
  * .rfmodal-backgroundimage - **background image or video for modal**
  * .rfmodal-wrapper.inner-modal - **layout container**
    * [See Desktop Retention Message](#desktop-retention-message)

### Mobile | (Video(web), retention\_modal(web), interstitial(web), ios, android\_os, tv\_os, roku\_os)

* .mobileFrameDisplay - **modal**
  * .mobileFrameInner - **inner frame**
    * [See close button](#close-button) **interstitial only**
    * .rfmodal-backgroundimage - **background image for modal**
    * .mobileWebModalWrapper - **modal wrapper**
      * .mobilewebModalContentWrapper - **content wrapper**
        * [See close button](#close-button) **everything, except interstitial**
        * .rfmodal-backgroundimage - **background video for modal**
          * .videoPosterImgDefault - **video poster**
        * [See TOS](#tos)
        * [See Mobile header and body](#mobile-header-and-body)
        * [See Input](#input)
        * [See Survey input](#survey-input)
        * [See Mobile footer](#mobile-footer)

### Mobile | (widget(web), bottom\_banner(web))

* .mweb-widget-container - **modal**
  * .mweb-phone-kit-bg - **inner frame**
    * .mweb-canvas-bound - **inner frame**
      * .mweb-widget-wrapper - **layout wrapper**
        * .rfmodal-backgroundimage - **background image for modal**
        * .mobilewebModalContentWrapper - **content wrapper**
          * [See close button](#close-button) **close button**
          * .mweb-widget-msg-container - **message wrapper**
            * .mweb-widget-spacer - **message spacer**
            * .mweb-widget-content-colm - **message content**
            * .rfmodal-footer-mobileweb - **buttons and countdown wrapper**
              * [See Mobile footer](#mobile-footer)
              * [See Input](#input)
            * [See Mobile header and body](#mobile-header-and-body)

### Desktop | (widget(web))

* .modal-overlay-style.widget-rf-promo - **modal**
  * .rf-widgetpromo-wrapper - **inner frame**
    * .rfmodal-backgroundimage - **background image for modal**
    * .rfmodal-wrapper - **content wrapper**
      * [See Desktop Retention Message](#desktop-retention-message)

### Desktop | (interstitial(web))

* .modal-overlay-style.interstitialModal - **modal**
  * [See close button](#close-button)
  * .rfmodal-content.outer-modal - **outer modal**
    * .rfmodal-wrapper.inner-modal - **inner modal**
      * [See Desktop Retention Message](#desktop-retention-message)

### Desktop | (text)

* .promo-text-wrapper - **prompt text**
  * [See close button](#close-button)
  * .promo-text-wrapper-container - **text container**
    * .promo-text-title - **text title**
    * .promo-text-message - **text message**

### Mobile | (text)

* .promo-text-wrapper-mobile - **prompt text**
  * [See close button](#close-button)
  * .promo-text-wrapper-container - **text container**
    * .promo-text-title - **text title**
    * .promo-text-message - **text message**

### Desktop | (horizontal, tile, vertical)

* .promo-tile-wrapper - **prompt tile**
  * [See close button](#close-button)
  * .promo-tile-backgroundimage - **background image**
  * .promo-tile-wrapper-container - **alignment class**
    * .tile-header-msg-wrp - **message wrapper**
      * [Promo Content](#promo-content)

### Mobile | (horizontal, tile, vertical)

* .rtile-mweb-content-wrapper - **prompt tile**
  * .rtile-mweb-content - **content wrapper**
    * .rfmodal-backgroundimage - **background image**
    * .rtile-mweb-content-msg - **message wrapper**
      * [Promo Content](#promo-content)

### Desktop, Mobile | (email)

* .pr-email-logo - **Logo**
* .pr-email-wrapper - **email content wrapper**
  * .pr-email-container - **email content container**
    * .pr-email-image - **email image**
  * .pr-email-msg - **email message container**
    * .pr-email-msg-title - **email message title**
    * .pr-email-msg-body - **email message body**
  * .pr-email-btn - **email buttons wrapper**
    * [See Input](#input)
    * [See Buttons promo](#buttons-promo)
* .pr-email-footer - **email footer (links)**

### Desktop | (bottom\_banner)

* .modal-overlay-style.banner-rf-promo - **banner**
  * .rfmodal-content.rf-bannerpromo-wrapper - **layout wrapper**
    * .rfmodal-backgroundimage - **background image**
    * .rfmodal-wrapper - **content wrapper**
      * [See Desktop Retention Message](#desktop-retention-message)

## Basic components

### Buttons

* .rfmodal-button-yes.primary-btn-p - **primary confirm button**
* .rfmodal-button-yes.secondary-btn-p - **secondary confirm button**
* .rfmodal-button-no - **no button**

### Buttons

* .promo-tile-wrapper-btn-accept - **primary confirm button**
* .promo-tile-wrapper-btn-accept.btn-ac-2 - **secondary confirm button**
* .promo-tile-wrapper-btn-no - **no button**

### Survey input

* .survey-wrapper(.center-align-mode | .right-align-mode) - **survey wrapper (alignment class)**
  * .rf-radio-group - **radio buttons wrapper**
    * .rf-radio-item - **radio item wrapper**

### Input

* .rfmodal-input-wrapper - **input container**
  * .rfmodal-input-label - **label for input**
  * .rfmodal-input-inputfield - **input**

### Close button

* .rfmodal-close - **modal close button**
  * `#rfmodal-close-icon` - **modal close icon**

### TOS

* .modal-privacy-tos - **TOS**

### Mobile header and body

* .rfmodal-header-mobileweb - **content header**
* .rfmodal-body-mobileweb - **content body**
  * .rfmodal-message-mobileweb - **content**

### Mobile footer

* .rfmodal-footer-mobileweb - **buttons and countdown wrapper**
  * [See Buttons](#buttons)
  * .rfmodal-countdown - **countdown label**

### Desktop Retention Message

* [See close button](#close-button)
* .video-volume-control - **volume button (video only)**
* .rfmodal-inner-wrapper - **content container**
  * .rfmodal-content-wrapper(.b-left-align | .b-right-align) - **alignment class**
    * .rfmodal-text-container - **content container**
      * [See TOS](#tos)
      * .rfmodal-header - **content header**
      * .rfmodal-body - **content body**
        * .rfmodal-message - **content**
      * [See Input](#input)
      * [See Survey input](#survey-input)
      * .rfmodal-footer - **footer container**
        * .rf-button-wrapper - **buttons and countdown wrapper**
          * .rf-buttons-inner - **button wrapper**
            * [See Buttons](#buttons)
          * .rfmodal-countdown - **countdown label (desktop / mobile)**

### Prompt Content

* .promo-tile-wrapper-header - **message header**
* .promo-tile-wrapper-body - **message body**
* .promo-tile-wrapper-footer - **message footer**
  * .promo-tile-wrapper-btn - **buttons wrapper**
    * [See Input](#input)
    * [See Buttons promo](#buttons-promo)

<br />

# Fine Tuning

While Redfast works out of the box, your customer experience can be further improved. This guide will provide potential optimizations you may want to employ.

## Absolutely positioning by inserting prompts

When dealing with absolutely positioned content it is best to avoid using the Live Tool. While the Live Tool provides a convenient way to quickly insert the appropriate HTML tag necessary to render prompts the best way to handle absolute content is as follows.

**Adding new content** 

1. Insert the zone tag into your app. 

`<div data-rf-zone="example-tag"></div>`

2. Wrap the tag and set a height for the Redfast html element using the Redfast IAB style standards.

`<div style="height: 200px"><div data-rf-zone="example-tag"></div></div>`

3. Initialize your page scroll effect

4. Resizing should be handled accordingly

## Absolutely positioning by replacing existing content

If you want to replace existing content it can be done with the Live Tool. This should be used sparingly. Make sure the dimensions of the prompt is the same as the content block you are replacing.

1. Using Live Tool select your prompt, click "Add" and hover over the appropriate sections.

2. Once the outline is completely solid you may click

3. The prompt will now replace the underlying content.

### Content delay for asynchronous data

Prompts may be delayed for a variety of reasons. Below are common solutions towards addressing most issues you may encounter using a combination of design and technical solutions.

1. Fixed content such as in the header does not appear immediately.

**Solution** - use an animation (css or behavior similar to skeleton loader)

2. Above fold content does not appear immediately

**Solution** - set an explicit height with a 1 second no content collapse timer (e.g. bandwidth constraints)

3. Redfast data loading too slowly

**JS tag Solution** - move Redfast up in your list of tags to allow for earlier loading

**Synchronous data loading Solution (Sledge hammer)** - wait for Redfast event data before proceeding to render app up to a maximum time limit

**Redfast Solution** - priority processing

4. User specific data loading too slowly\
   **Set default content solution** - Add a prompt set to All Users 

## Resizing issues

In some cases the user may run into issues with undersized or oversized browser windows. This can be improved using various CSS techniques. 

1. Width issues

**Solution** - Media queries

**Solution** - Scaling with transform or font size (e.g. 5vw)

2. Background image issues

**Solution** - Bake text into image

**Solution** - Background cover or contain, scaling with transform

**Solution** - Media queries

## Tools and Resources

Redfast provides you several resources to address the above issues.

1. Previewing using your styles with the Live Tool and Live Preview mode

2. Built in custom CSS overrides and ability to enhance existing elements with additional HTML

3. Direct Support from the Redfast technical team
