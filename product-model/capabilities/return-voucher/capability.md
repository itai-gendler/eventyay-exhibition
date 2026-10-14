---
availability:
- place: organizer-backend
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
---

# Return a voucher to the pool

Organizers take a code back from an organization so the pool can hand it out again, as long as it was neither redeemed nor emailed.
