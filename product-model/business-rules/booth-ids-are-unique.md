---
appliesTo:
- type: capability
  id: add-organization
- type: capability
  id: approve-exhibition-request
- type: capability
  id: edit-organization
references:
- kind: code
  role: implementation
  target: exhibition/models.py#generate_booth_id
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorInfoForm
---

# Every exhibitor has a booth ID, unique within the event

An exhibitor added or approved without a booth ID gets a generated one; organizations that do not exhibit have no booth and no lead scanning.
