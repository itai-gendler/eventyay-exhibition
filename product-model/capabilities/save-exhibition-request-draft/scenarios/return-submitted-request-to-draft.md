---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant changes the submitted request and chooses to save as draft
  kind: actor
  actor: applicant
  entities:
  - entity: exhibition-request
    effect: changes
    from: Submitted
    to: Draft
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
    - Submitted at
  contexts:
    web:
      place: event-website::signed-in::request-form
---

# Take a submitted request back to a draft

## Trigger

An applicant edits a submitted request that is not decided yet and chooses to save it as a draft.

## Outcome

The request is a draft again and waits for the applicant to submit it.
