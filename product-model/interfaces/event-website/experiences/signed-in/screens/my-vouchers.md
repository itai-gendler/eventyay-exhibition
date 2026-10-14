---
entities:
- entity: voucher
  shows:
  - Code
  - Product
  - Price effect
  - Value
  - Valid until
  - Maximum usages
  - Redeem link
- entity: voucher-redemption
  shows:
  - Voucher code
  - Attendee data
  - Order
  - Order status
  - Redeemed on
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionVouchersView
---

# My vouchers

An organization's vouchers and their redemptions, for its contact.
