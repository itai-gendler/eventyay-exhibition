---
kind: primary
routes:
  web: Web
steps:
- text: The Organizer chooses Approve on the review page
  kind: actor
  actor: organizer
  entities: []
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product accepts the request and keeps a copy of its details as accepted
  kind: product
  actor: organizer
  entities:
  - entity: exhibition-request
    effect: changes
    from: Submitted
    to: Accepted
    facts:
    - Profile at acceptance
    - Last updated
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product creates the organization profile from the request, generating a booth ID for an exhibitor without one
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: creates
    to: Unpublished
    facts:
    - Name
    - Description
    - Website
    - Contact page URL
    - Video URL
    - Slides
    - Logo
    - Banner
    - Booth name
    - Social media links
    - Extra links
    - Email
    - Exhibitor
    - Sponsor
    - Sponsor group
    - Booth ID
    - Access key
    - Position
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product places the acceptance email with the confirmation link in the outbox
  kind: product
  actor: organizer
  entities:
  - entity: queued-email
    effect: creates
    to: In outbox
    facts:
    - Kind
    - Recipient
    - Subject
    - Body
    - Language
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Contact email
    - Code
  contexts:
    web:
      place: organizer-backend::request-review
- text: The Product opens the new organization profile in its editor
  kind: product
  actor: organizer
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Description
    - Website
    - Contact page URL
    - Video URL
    - Slides
    - Logo
    - Banner
    - Booth name
    - Social media links
    - Extra links
  contexts:
    web:
      place: organizer-backend::organization-editor
---

# Approve a request on its review page

## Trigger

An organizer decides to accept a submitted request.

## Outcome

The request is accepted, its organization profile exists unpublished with a booth ID, the acceptance email waits in the outbox, and the organizer is in the new profile's editor.

## Edge cases

- A request manager who may not change the event's settings stays on the review page.
