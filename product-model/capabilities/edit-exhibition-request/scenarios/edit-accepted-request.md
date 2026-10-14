---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant opens the accepted request
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
    - Description
    - Language
    - Contact email
    - Website
    - Contact page URL
    - Video URL
    - Slides
    - Logo
    - Banner
    - Message to the organizers
    - Social media links
    - Extra links
    - Booth name
    - Answers
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The organization name cannot be changed once the request is accepted
  kind: condition
  entities:
  - entity: exhibition-request
    effect: reads
    facts:
    - Organization name
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Applicant changes other details and chooses Save
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
    facts:
    - Description
    - Website
    - Logo
    - Banner
    - Social media links
    - Answers
    - Last updated
    - Edited after acceptance
    - Profile at acceptance
  contexts:
    web:
      place: event-website::signed-in::request-form
- text: The Product copies the applicant's details onto the organization profile in the request's language
  kind: product
  actor: applicant
  entities:
  - entity: organization-profile
    effect: changes
    facts:
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
      place: event-website::signed-in::request-form
---

# Change an accepted request

## Trigger

An applicant whose request was accepted updates the organization's details.

## Outcome

The organization profile shows the new details, and the organizers see what changed since acceptance.

## Edge cases

- The request stays accepted or confirmed; saving it as a draft is not possible once accepted.
- The organization's email is also copied, from the request's contact email.
