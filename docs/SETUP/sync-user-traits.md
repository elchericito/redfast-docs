---
title: Sync User Traits
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
Depending on the selected use case, think of the users you’d like to target and list the user attributes required for targeting.\
**For example:**

| Item                | Example                  | Interval  | Source        |
| :------------------ | :----------------------- | :-------- | :------------ |
| Current Plan        | Trial / Monthly / Annual | Daily     | CSV           |
| Customer Since      | Time in months           | Daily     | CSV           |
| Next bill date      | Date                     | Daily     | CSV           |
| Payment method      | Credit card/IOS          | Daily     | CSV           |
| Last payment status | Failed                   | Real Time | Segment Event |

Create target users CSV with the attributes. See example file in shared folder for format.\
Note that a CSV is not required if your selected use cases do not require any attribute based targeting.

You can learn more about importing user traits [here](user-traits)
