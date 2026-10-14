---
availability:
- place: organizer-backend
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
- kind: code
  role: implementation
  target: exhibition/utils.py#claim_pool_vouchers
- kind: code
  role: implementation
  target: exhibition/utils.py#resolve_voucher_defaults
---

# Assign vouchers

Organizers give an organization unassigned codes from its voucher pool, without emailing them.
