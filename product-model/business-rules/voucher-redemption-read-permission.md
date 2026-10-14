---
appliesTo:
- type: entity
  id: voucher-redemption
  effect: reads
permits:
- actors:
  - lead-scanning-app
  when:
  - entity: organization-profile
    fact: Voucher access
    is: 'On'
- related:
  - verb: is redeemed in
    entity: voucher
  - verb: holds
    entity: organization-profile
  - verb: manages
    entity: exhibitor-contact
  when:
  - entity: organization-profile
    fact: Voucher access
    is: 'On'
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#user_can_view_vouchers
- kind: code
  role: implementation
  target: exhibition/api.py#VoucherRedemptionRetrieveView
---

# Only an organization with voucher access sees who redeemed its vouchers

The contact of an active organization and its lead scanning app see the redemptions of its vouchers while it has voucher access.
