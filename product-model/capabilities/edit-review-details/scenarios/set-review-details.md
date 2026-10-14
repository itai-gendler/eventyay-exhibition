---
kind: primary
routes:
  web: Web
steps:
- text: The Request manager marks the request as exhibitor and sponsor, picks a sponsor group, enters a booth ID and name, and chooses Save
  kind: actor
  actor: request-manager
  entities:
  - entity: exhibition-request
    effect: changes
    facts:
    - Exhibitor
    - Sponsor
    - Sponsor group
    - Booth ID
    - Booth name
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product clears the group of a request that is not a sponsor, and the booth of one that does not exhibit, and says the details are saved
  kind: product
  actor: request-manager
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
---

# Set type, group and booth

## Trigger

A request manager prepares a submitted request for approval.

## Outcome

The request carries the chosen type, sponsor group and booth; the change is recorded in its history.
