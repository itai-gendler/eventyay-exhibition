---
kind: alternative
routes:
  web: Web
steps:
- text: The Exhibitor contact opens the vouchers of their organization
  kind: actor
  actor: exhibitor-contact
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
- text: The organization profile is active and has voucher access
  kind: condition
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Voucher access
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
- text: The Exhibitor contact reads each unredeemed assigned voucher with its redeem link
  kind: actor
  actor: exhibitor-contact
  entities:
  - entity: voucher
    effect: reads
    facts:
    - Code
    - Product
    - Price effect
    - Value
    - Valid until
    - Maximum usages
    - Redeem link
  contexts:
    web:
      place: event-website::signed-in::my-vouchers
---

# See my codes still to hand out

## Trigger

An exhibitor contact opens their organization's vouchers in My Exhibitions and the Open tab.

## Outcome

The contact sees the codes nobody has redeemed yet, each with a redeem link, and how many were issued and redeemed.

## Edge cases

- Without voucher access, or for someone else's organization, the page is not found.
