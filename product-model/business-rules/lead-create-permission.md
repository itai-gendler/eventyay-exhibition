---
appliesTo:
- type: entity
  id: lead
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
  target: exhibition/api.py#LeadCreateView
---

# Only an organization that may scan leads records them

The lead scanning app records leads with the access key of an organization whose lead scanning is on.
