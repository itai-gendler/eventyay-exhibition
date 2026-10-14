---
entities:
- entity: custom-field
  shows:
  - Question
- entity: organization-profile
  shows:
  - Name
  collects:
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
  - Lead scanning
  - Lead access
  - Voucher access
  - Lead scanning behavior
  - Related sessions
  - Access key
  - Position
- entity: exhibition-request
  collects:
  - Answers
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorEditView
---

# Organization editor

Adding, changing or deleting one organization profile.
