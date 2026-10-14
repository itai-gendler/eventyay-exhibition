---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
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
permits:
- related:
  - verb: owns
    entity: applicant
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
---

# Only the applicant changes what their request says

The organization's details, the language and the message in a request are its applicant's to change.
