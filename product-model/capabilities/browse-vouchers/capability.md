---
availability:
- place: organizer-backend
- place: event-website::signed-in
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionVouchersView
- kind: code
  role: implementation
  target: exhibition/utils.py#exhibitor_unredeemed_vouchers
---

# Browse vouchers

The codes an organization holds: for organizers, every assigned code and whether it was redeemed; for the exhibitor contact in My Exhibitions, the codes nobody has redeemed yet, with their redeem links.
