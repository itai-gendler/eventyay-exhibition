---
entities:
- entity: voucher
  shows:
  - Code
  - Product
  - Redeemed
  - Price effect
  - Valid until
- entity: queued-email
  shows:
  - Sent at
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
---

# Organization vouchers

One organization's assigned vouchers.
