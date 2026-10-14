---
appliesTo:
- type: entity
  id: voucher
  effect: removes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
---

# Only organizers return vouchers to the pool

Codes go back to the pool only when organizers return them.
