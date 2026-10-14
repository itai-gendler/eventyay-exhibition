---
appliesTo:
- type: capability
  id: browse-sponsor-groups
- type: capability
  id: show-sponsor-group-on-front-page
- type: capability
  id: publish-organization
references:
- kind: code
  role: implementation
  target: exhibition/signals.py#presale_supported_by
---

# The front page shows only published sponsors with a logo

Only sponsor groups shown on the front page appear, each with its published, active sponsors that have a logo, by level and position.
