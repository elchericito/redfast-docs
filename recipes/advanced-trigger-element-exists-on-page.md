---
title: Advanced Trigger - Element exists on page
description: Recipe Description
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```javascript JavaScript
const attachment = document.querySelector(".attachments > .attachment");
return !!attachment;
```

```json Response Example
{"success":true}
```

# 1. Review Default Advanced Trigger

<!-- javascript@1-2 -->

Open "[DEFAULT] Element exists on page" trigger within Settings > Triggers > Advanced Triggers

# 2. Update Query Selector

<!-- javascript@1 -->

Update query selector for the element you are looking for. It can contain html element, classname, id, pseudo element etc.

# 4. Copy Advanced Trigger

<!-- javascript@1-2 -->

Copy all lines to a new Advanced Trigger with a name of your choice

# 5. Save Changes

<!-- javascript@1-2 -->

Save the Advanced Trigger and utilize it within your prompt trigger. Note that it may take a few minutes before the advanced trigger code is available for use on your site/app.