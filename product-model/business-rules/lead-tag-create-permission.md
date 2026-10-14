---
appliesTo:
- type: entity
  id: lead-tag
  effect: creates
permits:
- actors:
  - lead-scanning-app
  when:
  - entity: organization-profile
    fact: Lead scanning
    is: 'On'
references:
- kind: code
  role: implementation
  target: exhibition/api.py#LeadUpdateView
---

# Only an organization that may scan leads adds lead tags

Tags are remembered while the organization's lead scanning is on.
