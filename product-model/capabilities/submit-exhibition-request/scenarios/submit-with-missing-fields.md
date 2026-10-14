---
kind: validation
routes:
  web: Web
steps:
- text: The Applicant chooses Submit request with a required field empty
  kind: actor
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: A required standard field, link list or visible custom field has no value
  kind: condition
  entities:
  - entity: event
    effect: reads
    facts:
    - Standard fields
  - entity: custom-field
    effect: reads
    facts:
    - Required
    - Depends on
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product keeps the form open and marks each missing field
  kind: product
  actor: applicant
  entities: []
  contexts:
    web:
      place: event-website::signed-in::request-form
---

# Required fields are missing

## Trigger

An applicant submits without a required field, such as the logo or a required custom field.

## Outcome

Nothing is submitted; the form shows which fields need an answer.

## Edge cases

- A custom field hidden because of another field's answer never blocks submitting, and its answer is not kept.
- Uploads above the size limit and slides that are not a PDF are refused the same way.
