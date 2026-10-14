---
appliesTo:
- type: entity
  id: lead
  effect: changes
  facts:
  - Note
  - Tags
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

# Only an organization that may scan leads notes and tags them

Notes and tags are kept while the organization's lead scanning is on.
