---
entities:
- entity: organization-profile
  shows:
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
  collects:
  - Description
  - Website
  - Logo
  - Banner
  - Booth name
  - Social media links
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionEditView
---

# Profile editor

Where the contact of an organizer-added profile edits its public details.
