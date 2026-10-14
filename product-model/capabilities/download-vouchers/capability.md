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
  target: exhibition/utils.py#build_voucher_csv
---

# Download vouchers

A CSV of an organization's codes with their redeem links: all of them for organizers, the unredeemed ones for the exhibitor contact.
