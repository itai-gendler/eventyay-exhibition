---
appliesTo:
- type: capability
  id: browse-exhibition
- type: capability
  id: view-exhibitor
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#public_exhibitors_queryset
---

# The public exhibition shows only published, active exhibitors with a logo and a banner

Sponsor-only profiles, inactive or unpublished ones, and those missing a logo or banner are left out of the Exhibition page and their pages are not found; the Exhibition tab appears only while at least one exhibitor is shown.
