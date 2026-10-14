---
kind: primary
routes:
  web: Web
steps:
- text: The Exhibitor contact opens My Exhibitions
  kind: actor
  actor: exhibitor-contact
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-exhibitions
- text: The Product lists the person's requests and the active or inactive profiles added for their verified email, with an edit link and, where voucher access is on, a vouchers link
  kind: product
  actor: exhibitor-contact
  entities:
  - entity: account
    effect: reads
    facts:
    - Verified email addresses
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Voucher access
    - Added by the organizer
  contexts:
    web:
      place: event-website::signed-in::my-exhibitions
- text: The Exhibitor contact reads each organization profile's name and status
  kind: actor
  actor: exhibitor-contact
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  contexts:
    web:
      place: event-website::signed-in::my-exhibitions
---

# See my exhibitions

## Trigger

An exhibitor contact opens My Exhibitions from their dashboard.

## Outcome

The contact sees each request and added profile, newest event first, with what they can open.

## Edge cases

- My Exhibitions is offered only to someone with a request or an added profile.
- The list can be searched by name and narrowed to one event.
