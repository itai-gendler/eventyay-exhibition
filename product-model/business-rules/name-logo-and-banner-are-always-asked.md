---
appliesTo:
- type: capability
  id: change-exhibitor-form-settings
- type: capability
  id: submit-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/models.py#REQUEST_DEFAULT_FIELDS
---

# The organization name, logo and banner are always asked and required

These standard fields cannot be turned off or made optional, because a profile needs them to appear on the public event website.
