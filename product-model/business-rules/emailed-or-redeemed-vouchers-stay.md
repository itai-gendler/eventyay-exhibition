---
appliesTo:
- type: capability
  id: return-voucher
- type: capability
  id: email-vouchers
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
---

# A redeemed or emailed voucher is never returned to the pool

A code that was redeemed, or that a voucher email listed, stays with the organization; it can only be deleted in the ticket shop.

## Rationale

Returning it would hand a code to someone else while the first organization still holds it in its inbox.
