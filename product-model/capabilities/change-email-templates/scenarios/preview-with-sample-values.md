---
kind: alternative
routes:
  web: Web
steps:
- text: The Organizer chooses to preview the vouchers template
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::email-templates
- text: The Product renders the draft text in every language with sample voucher codes and links
  kind: product
  actor: organizer
  entities:
  - entity: event
    effect: reads
    facts:
    - Content languages
  contexts:
    web:
      place: organizer-backend::email-templates
---

# Preview a template

## Trigger

An organizer previews the vouchers email while writing it.

## Outcome

The organizer sees the text in each language with sample values for the placeholders.
