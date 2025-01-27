---
title: Inline
excerpt: 'Inline Styles: horizontal banner, vertical banner, tile, and text bar'
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
These 4 prompts occupy particular pieces of real estate on your site/application. Since the prompts live alongside your content we frequently refer to these as inlines.

<Image align="center" className="border" border={true} src="https://files.readme.io/3306b54-Screenshot_2024-04-18_193019.png" />

Inlines are defined inside of [zones](zones). Once a zone is defined, any prompt designated for it will be shown in the locations specified. For example, a horizontal prompt could be added into the **Web Featured** horizontal zone.

<Image align="center" className="border" border={true} src="https://files.readme.io/e0c5481-Screenshot_2024-04-18_191758.png" />

A single zone may contain one or more items of the same type. For instance, you can place multiple horizontal prompts within a zone to render a slider on your site. Multiple items can be displayed as:

* A stack where items are behind one another. The user sees the second item when he has completed an interaction with the first item.
* A list where items are shown beside each other. This is useful to display a row of personalized items on your site.
* A slider where items are shown beside each other in a carousel or slider mode where only one item is visible at a time. When this display type is selected, the SDK can optionally render:
  * Bullet indicators allowing users to navigate between slides
  * Automatic rotation of slides with a configurable number of seconds per slide

## Inline Types

### Horizontal

A horizontal prompt is usually created in a zone with a landscape layout i.e. larger width and smaller height aspects. It is expected to fit edge to edge of screen width or margin to margin of content layout width. 

Typical zones are top or bottom of the screen and sometimes in between page sections. It may be clickable and/or set to a timer. It may include an optional call to action button. A horizontal banner may be hidden once clicked or continue to be shown. 

The recommended aspect ratios are: 2x1, 4x1, **6x1**, 8x1, 10x1

<Image align="center" className="border" border={true} src="https://files.readme.io/994d3cd-image.png" />

### Vertical

A vertical prompt is created in a zone with portrait layout i.e. larger height and smaller width aspects. It is expected to fit edge to edge from top to bottom or margin to margin vertically between page layout elements. 

Typical zones are on the right or left edges of the screen or page layout. It may be clickable and/or set to a timer. It may include an optional call to action button. A vertical banner may be hidden once clicked or continue to be shown.

The recommended aspect ratios are: 1x2, **1x3**, 1x4

<Image align="center" className="border" border={true} src="https://files.readme.io/a1fb469-image.png" />

### Tile

Tiles are usually rectangle or square zones with very closely measured height and width aspects. Typical zones are tiles in grid layouts. Usually they are small to medium-sized zones. A square image with text and that can be clicked. A tile may be hidden once clicked or continue to be shown. 

The recommended aspect ratios are: 2x1, 4x1, **6x1**, 8x1, 10x1

<Image align="center" className="border" border={true} src="https://files.readme.io/5729a7f-image.png" />

### Text Only

The text bar is created in a text only zone that can be clicked. It may be hidden once clicked or continue to be shown. 

The recommended aspect ratios are: 6x1, 8x1, 10x1

<Image align="center" className="border" border={true} src="https://files.readme.io/392d0bc-image.png" />

<br />

## How-to-video

This guide will teach you how to create a horizontal banner that is visible to all users who visit our home page. The instructions for creating vertical, tile, and text prompts are exactly the same.

<Embed url="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" title="iframe" provider="loom.com" href="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

***

## Step-by-step

* [ ] Create a Zone

  * [ ] Go to Settings > Zones > New Zone\
    This zone will live on the home page in the top banner section. The identifier should not have any spaces. You can add as many prompts as you want into the zone.

    <Image align="center" className="border" border={true} src="https://files.readme.io/0e07cb5-image.png" />

    <Image align="center" className="border" border={true} src="https://files.readme.io/60a9382-inline2.png" />

* [ ] Create an inline prompt 

  * [ ] Go to Prompts > New Prompt.\
    Now we can create horizontal prompts that will be shown inside the zone. While the zone should typically be considered permanent real estate, the prompts inside can be added and removed as desired.

    <Image align="center" className="border" border={true} src="https://files.readme.io/564d84a-image.png" />

  * [ ] Select "Desktop and Mobile" since we are creating a prompt for the browser. Then select the horizontal prompt.

    <Image align="center" className="border" border={true} src="https://files.readme.io/664a781-image.png" />

  * [ ]  Name your prompt, create a description, select the zone and hit Submit.

    <Image align="center" className="border" border={true} src="https://files.readme.io/c8c3561-image.png" />

  * [ ] Add segments, limits (optional), schedule (optional), and action.

  * [ ] Click the 'Edit prompt design' button to update the creative

    <Image align="center" className="border" border={true} src="https://files.readme.io/6a6227a-Screenshot_2024-04-22_173653.png" />

  * [ ] Design.

    This is where the magic happens. Feel free to tinker with the settings and see your changes live in the preview on the left. In our example we will leave it as is, but you should feel comfortable making changes to any settings within the highlighted area. 

    Background image size varies by device. Click here for a [zip file with sample background images](/images/samples.zip).

    <Image align="center" className="border" border={true} src="https://files.readme.io/0d80810-Screenshot_2024-04-22_174308.png" />

  * [ ] Publish your newly created item

    <Image align="center" className="border" border={true} src="https://files.readme.io/a55eac9-Screenshot_2024-04-22_174752.png" />

* [ ] Go to the zone list view. This page shows all current prompts running in the zone. If you have more than one prompt you can change the 'Style' to a slider or list.

  <Image align="center" className="border" border={true} src="https://files.readme.io/dcbb8c2-Screenshot_2024-04-22_175035.png" />

<br />

## Integration

Redfast provides two paths of integration for websites - 1) the Live Tool integration and 2) custom developer integration. For the sake of this guide the Live Tool integration may be sufficient.

### Live Tool Implementation

This integration will open the the Live Tool panel as an overlay over your site. Then you can point and click to insert the zone in your desired location.

* [ ] Click the Live Tool button and select the domain

  <Image align="center" className="border" border={true} src="https://files.readme.io/7cb2ded-Screenshot_2024-04-22_175333.png" />

  ![](https://files.readme.io/03543e0-Screenshot_2024-04-22_175548.png)
* [ ] Expand the Live Tool panel

  <Image align="center" className="border" border={true} src="https://files.readme.io/a1fe85f-image.png" />
* [ ] Open the 'Add' tab
* [ ] Click 'Add' on the zone you created earlier

  ![](https://files.readme.io/598537b-image.png)
* [ ] Hover over the part of the site you wish to add the zone.\
  Move your mouse closer to the edge will show a thick outline. In this case the thicker portion of the outline is shown at the top. This indicates we will be inserting above the highlighted section. Which in this case is the 'New Releases'.

  ![](https://files.readme.io/7878719-image.png)
* [ ] Click to add your zone. Your banner will now appear

  ![](https://files.readme.io/997c32a-image.png)
* [ ] That's it!

### Developer Guide

* [ ] Retrieve the identifier
* [ ] You can give the identifier to your developer or you can add it to your app yourself.
* [ ] That's it!

> 📘 Absolutely positioning by inserting prompts
>
> When dealing with absolutely positioned content it is best to avoid using the Live Tool. While the Live Tool provides a convenient way to quickly insert the appropriate HTML tag necessary to render prompts the best way to handle absolute content is as follows.
>
> Adding new content
>
> 1. Insert the zone tag into your app.
>
> `<div data-rf-zone="example-tag"></div>\`
>
> 2. Wrap the tag and set a height for the Redfast html element using the Redfast IAB style standards.
>
> `<div style="height: 200px"><div data-rf-zone="example-tag"></div></div>\`
>
> 3. Initialize your page scroll effect
>
> 4. Resizing should be handled accordingly

> 📘 Absolutely positioning by replacing existing content
>
> If you want to replace existing content it can be done with the Live Tool. This should be used sparingly. Make sure the dimensions of the prompt is the same as the content block you are replacing.
>
> 1. Using Live Tool select your prompt, click “Add” and hover over the appropriate sections.
>
> 2. Once the outline is completely solid you may click
>
> 3. The prompt will now replace the underlying content.

### More tips and tricks

#### Content delay for asynchronous data

Prompts may be delayed for a variety of reasons. Below are common solutions towards addressing most issues you may encounter using a combination of design and technical solutions.

**Fixed content such as in the header does not appear immediately.**

Solution - use an animation (css or behavior similar to skeleton loader)

**Above fold content does not appear immediately**

Solution - set an explicit height with a 1 second no content collapse timer (e.g. bandwidth constraints)

**Redfast data loading too slowly**

JS tag Solution - move Redfast up in your list of tags to allow for earlier loading

Synchronous data loading Solution (Sledge hammer) - wait for Redfast event data before proceeding to render app up to a maximum time limit

Redfast Solution - priority processing

**User specific data loading too slowly** 

Set default content solution - Add a prompt set to All Users

**Resizing issues**\
In some cases the user may run into issues with undersized or oversized browser windows. This can be improved using various CSS techniques.

1. Width issues

Solution - Media queries

Solution - Scaling with transform or font size (e.g. 5vw)

2. Background image issues

Solution - Bake text into image

Solution - Background cover or contain, scaling with transform

Solution - Media queries

Tools and Resources\
Redfast provides you several resources to address the above issues.

1. Previewing using your styles with the Live Tool and Live Preview mode

2. Built in custom CSS overrides and ability to enhance existing elements with additional HTML

3. Direct Support from the Redfast technical team
