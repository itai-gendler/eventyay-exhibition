---
kind: primary
routes:
  api: API
steps:
- text: The Lead scanning app asks for the tags with the access key
  kind: actor
  actor: lead-scanning-app
  entities: []
  contexts:
    api:
      place: exhibitor-api
- text: The Product returns the organization's lead tags, most used first
  kind: product
  actor: lead-scanning-app
  entities:
  - entity: lead-tag
    effect: reads
    facts:
    - Name
    - Use count
  contexts:
    api:
      place: exhibitor-api
---

# Fetch the tags

## Trigger

Booth staff start tagging a lead.

## Outcome

The app offers the organization's tags.

## Edge cases

- With lead scanning off, the app is refused.
