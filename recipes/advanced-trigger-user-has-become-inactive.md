---
title: Advanced Trigger - User has become inactive
description: Recipe Description
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```javascript JavaScript
if (!window.loaded) {
  window.lastActiveTs = +new Date();
  function updateLastTs() {
    window.lastActiveTs = +new Date();
  }
  document.onmousemove = updateLastTs;
  document.onkeypress = updateLastTs;
  window.loaded = true;
}
const minuteElapsed = +new Date() - window.lastActiveTs > 30 * 1000; //e.g. change the 30 here to 120 for 2 seconds

return minuteElapsed;
```

```json Response Example
{"success":true}
```

# 1. Review Default Advanced Trigger

<!-- javascript@1-13 -->

Open "[DEFAULT] User has become inactive" trigger within Settings > Triggers > Advanced Triggers

# 2. Update inactive time

<!-- javascript@11 -->

