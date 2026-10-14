---
appliesTo:
- type: capability
  id: save-exhibition-request-draft
- type: capability
  id: submit-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestForm
---

# A draft needs only the organization name

Saving as a draft skips every other required field; submitting enforces them all.
