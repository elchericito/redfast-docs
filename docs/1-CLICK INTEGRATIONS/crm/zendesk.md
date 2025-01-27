---
title: Zendesk
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
## Required Settings

* Domain
* API Key (aka API Token)
* Username

## Supported Actions

| Action                                                      | Description                                                         | User Dependencies             | Additional Instructions                                                                                     |
| ----------------------------------------------------------- | ------------------------------------------------------------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Create support ticket with notification of offer acceptance | Creates a support ticket with information about the user and prompt | n/a                           | n/a                                                                                                         |
| Set priority of all existing tickets                        | Sets priority attribute for all tickets created by the user         | zendesk\_id or email\_address | Select the priority level on the prompt screen                                                              |
| Assign all existing tickets to a specific agent             | Assigns all tickets created by the user to one agent                | zendesk\_id or email\_address | Select the agent on the prompt screen. Manage agents in the Zendesk dashboard under Admin > People > Agents |
| Suspend user                                                | Sets the user to suspended state                                    | zendesk\_id or email\_address | n/a                                                                                                         |
| Restore suspended user                                      | Restores the user from suspended state                              | zendesk\_id or email\_address | n/a                                                                                                         |
| Assign all existing tickets to a group                      | Assigns all tickets created by the user to a group                  | zendesk\_id or email\_address | Select the group on the prompt screen. Manage groups in the Zendesk dashboard under Admin > People > Groups |
| Delete all tickets                                          | Deletes all tickets created by the user                             | zendesk\_id or email\_address | n/a                                                                                                         |
| Set status of all existing tickets                          | Sets status of all tickets created by the user                      | zendesk\_id or email\_address | Select the status on the prompt screen                                                                      |
| Delete and spam all existing tickets                        | Marks all tickets created by the user as spam                       | zendesk\_id or email\_address | n/a                                                                                                         |

## Additional Information

[Zendesk API token](https://support.zendesk.com/hc/en-us/articles/226022787-Generating-a-new-API-token-)
