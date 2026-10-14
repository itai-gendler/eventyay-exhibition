---
appliesTo:
- type: capability
  id: edit-exhibition-request
- type: capability
  id: approve-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestForm
---

# An accepted request's organization name is locked

Once a request is accepted or confirmed, its applicant can no longer change the organization name; the organizers can.
