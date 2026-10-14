---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  from: Inactive
  to: Unpublished
permits:
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#create_exhibitor_from_request
---

# A profile becomes active again only by approving its request

Approving a rejected, withdrawn or reopened request again brings its profile back, unpublished.
