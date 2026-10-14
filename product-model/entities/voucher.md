---
domain: exhibitors-and-sponsors
relations:
- entity: voucher-redemption
  verb: is redeemed in
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitorVoucher
- kind: code
  role: implementation
  target: exhibition/utils.py#claim_pool_vouchers
---

# Assigned voucher

A ticket shop voucher code from the event's pool that an organization holds to hand out; attendees who redeem it count as the organization's.

## Information kept

- **Code** — the voucher code
- **Product** — the product it applies to
- **Price effect** — how it changes the price
- **Value** — the discount or price
- **Valid until** — its expiry
- **Maximum usages** — how many times it can be redeemed
- **Redeemed** — how many times it was redeemed
- **Redeem link** — a ticket shop link that applies the code
- **Assigned at** — when the organization received it
