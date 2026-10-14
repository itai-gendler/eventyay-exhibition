---
appliesTo:
- type: entity
  id: voucher
  effect: creates
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
---

# Only organizers assign vouchers to organizations

Codes are taken from the pool only by those who may change the event's settings.
