---
appliesTo:
- type: entity
  id: organization-profile
  effect: creates
permits:
- actors:
  - organizer
  - request-manager
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorCreateView
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
---

# Organizers add organization profiles, and approving a request creates one

Organizers add profiles by hand or through the organizer API; whoever may decide requests creates one by approving a request.
