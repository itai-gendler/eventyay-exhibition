---
appliesTo:
- type: entity
  id: lead
  effect: reads
  facts:
  - Attendee data
permits:
- actors:
  - lead-scanning-app
  when:
  - entity: organization-profile
    fact: Lead access
    is: 'On'
references:
- kind: code
  role: implementation
  target: exhibition/api.py#LeadRetrieveView
- kind: code
  role: implementation
  target: exhibition/api.py#_visible_attendee
---

# Only an organization allowed to view collected leads sees their attendee details

An organization may keep scanning without seeing whom it scanned: the attendee details of its leads are returned only while it may view and export collected leads.
