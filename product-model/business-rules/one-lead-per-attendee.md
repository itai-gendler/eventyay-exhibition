---
appliesTo:
- type: capability
  id: scan-lead
- type: entity
  id: lead
  effect: creates
references:
- kind: code
  role: implementation
  target: exhibition/api.py#LeadCreateView
---

# An attendee is one lead per organization

Scanning an attendee the organization already has makes no second lead.
