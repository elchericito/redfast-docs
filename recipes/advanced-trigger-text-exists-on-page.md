---
title: Advanced Trigger - Text exists on page
description: >-
  This recipe will help you to configure a trigger that will look for a specific
  text on the page.
hidden: true
recipe:
  color: '#018FF4'
  icon: 🦉
---
```javascript JavaScript
const subject = document.querySelector(".categories > .category:first-child");
if (subject) {
  return subject.textContent === "Sorry you dont have a cc on file";
}
return false;
```

```json Response Example
{"success":true}
```

# 1. Review Default Advanced Trigger

<!-- javascript@1-5 -->

Open "[DEFAULT] Text exists on page" trigger within Settings > Triggers > Advanced Triggers

# 2. Update Query Selector

<!-- javascript@1 -->

Update query selector for the element you are looking for. It can contain html element, classname, id, pseudo element etc.

# 3. Update Text Content

<!-- javascript@3 -->

Update text content to match the text you are looking for inside the element.

# 4. Copy Advanced Trigger

<!-- javascript@1-5 -->

Copy all lines to a new Advanced Trigger with a name of your choice

# 5. Save Changes

<!-- javascript@1-5 -->

Save the Advanced Trigger and utilize it within your prompt trigger. Note that it may take a few minutes before the advanced trigger code is available for use on your site/app.