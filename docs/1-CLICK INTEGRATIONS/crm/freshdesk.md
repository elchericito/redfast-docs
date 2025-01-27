---
title: Freshdesk
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

- Domain
- API Key

## Supported Actions

| Action                                                      | Description                                                        | User Dependencies             | Additional Instructions                 |
| :---------------------------------------------------------- | :----------------------------------------------------------------- | :---------------------------- | :-------------------------------------- |
| Create support ticket with notification of offer acceptance | Creates a support ticket with information about the user and promo |                               | n/a                                     |
| Update existing tickets priority                            | Update priority for all tickets created by the user                | freshdesk_id or email_address | Bulk update fields on the prompt screen |
| Update existing tickets status                              | Update status for all tickets created by the user                  | freshdesk_id or email_address | Bulk update fields on the prompt screen |
| Update existing tickets responder                           | Update responder for all tickets created by the user               | freshdesk_id or email_address | Bulk update fields on the prompt screen |
| Update existing tickets group                               | Update group for all tickets created by the user                   | freshdesk_id or email_address | Bulk update fields on the prompt screen |
| Update existing tickets source                              | Update source for all tickets created by the user                  | freshdesk_id or email_address | Bulk update fields on the prompt screen |
| Soft delete a contact                                       | Sets the contact to a deleted state                                | freshdesk_id or email_address | n/a                                     |
| Restore a contact                                           | Restores the contact from a deleted state                          | freshdesk_id or email_address | n/a                                     |
| Delete all tickets                                          | Deletes all tickets created by the contact                         | freshdesk_id or email_address | n/a                                     |
| Spam all existing tickets                                   | Marks all tickets created by the user as spam                      | freshdesk_id or email_address | n/a                                     |

## Additional Information

[Freshdesk API Token](https://support.freshdesk.com/support/solutions/articles/215517-how-to-find-your-api-key)