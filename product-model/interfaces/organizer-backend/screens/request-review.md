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
  - Internal review notes
  - Profile at acceptance
  - Edited after acceptance
  collects:
  - Exhibitor
  - Sponsor
  - Sponsor group
  - Booth ID
  - Booth name
  - Internal review notes
- entity: account
  shows:
  - Name
  - Email
- entity: queued-email
  shows:
  - Subject
  - Recipient
  - Sent at
  - Send at
- entity: request-history
  shows:
  - Who
  - What happened
  - From state
  - To state
  - When
- entity: sponsor-group
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestDetailView
---

# Request review

One request's review page.
