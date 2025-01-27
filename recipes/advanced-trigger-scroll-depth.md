---
title: Advanced Trigger - Scroll Depth
description: Recipe Description
hidden: true
recipe:
  color: '#018FF4'
  icon: 🦉
---
```javascript JavaScript22
let height = window.innerHeight + window.pageYOffset;
const percent = document.documentElement.scrollHeight * 0.7;

return height >= percent;
```

```json Response Example
{"success":true}
```

# Review Default Advanced Trigger



Open "[DEFAULT] User scrolls over 50%" trigger within Settings > Triggers > Advanced Triggers

# Update Percent Scroll Depth

<!-- javascript@2 -->

Update `percent` to the intended scroll depth. This example is for 70%.

# Copy Advanced Trigger

<!-- javascript@1-4 -->

Copy all lines to a new Advanced Trigger with a name of your choice

# Save Changes

<!-- javascript@1-4 -->

Save the Advanced Trigger and utilize it within your prompt trigger. Note that it may take a few minutes before the advanced trigger code is available for use on your site/app.