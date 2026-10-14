---
entities:
- entity: exhibition-request
  shows:
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
  collects:
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
  - Code
  - Exhibitor
  - Sponsor
  - Last updated
  - Submitted at
  - Edited after acceptance
  - Profile at acceptance
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
---

# Request form

The exhibitor form, for a new request or an existing one.
