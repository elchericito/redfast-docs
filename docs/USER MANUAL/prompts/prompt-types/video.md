---
title: Video
excerpt: Best practices for delivering video prompts
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
A video prompt allows you to display a video within a popup modal.

<Embed url="https://www.loom.com/embed/fe1d6051af2d417eb95dddb4702014f1?sid=9ccd4e6f-3e97-474d-8100-a4afc1561db2" title="iframe" provider="loom.com" href="https://www.loom.com/embed/fe1d6051af2d417eb95dddb4702014f1?sid=9ccd4e6f-3e97-474d-8100-a4afc1561db2" typeOfEmbed="iframe" height="400px" width="100%" iframe="true" />

The following video specific configuration parameters are available for video prompts:

* Video URL: This is a link to the source video file to played. While MP4 format is fully supported by most browsers, we recommend using HLS format links to minimize buffering. MP4 files should be less than 25 MB for best performance.
* Video Cover: You can optionally upload a poster image to display before and after the video is played.
* Mute: Best practice is to set video prompts that autoplay to be muted.
* Loop: This allows you to play the specified video on a loop when it reaches the end.
* Autoplay: When enabled, the video will play as soon as the prompt is shown. Note that most browsers will restrict autoplay videos to be muted.