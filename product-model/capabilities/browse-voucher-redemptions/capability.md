---
availability:
- place: event-website::signed-in
- place: exhibitor-api
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionVouchersView
- kind: code
  role: implementation
  target: exhibition/api.py#VoucherRedemptionRetrieveView
- kind: code
  role: implementation
  target: exhibition/utils.py#exhibitor_voucher_redemptions
- kind: code
  role: implementation
  target: exhibition/utils.py#attendee_field_specs
---

# Browse voucher redemptions

The tickets bought with an organization's vouchers, newest first, with the attendee details the event shares and the order's status: in My Exhibitions for the exhibitor contact, and through the exhibitor API for the lead scanning app, when the organization has voucher access.
