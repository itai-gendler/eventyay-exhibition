---
appliesTo:
- type: capability
  id: edit-exhibition-request
- type: capability
  id: submit-exhibition-request
- type: capability
  id: save-exhibition-request-draft
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
---

# Drafts and submitted requests change only while the call is open

Applicants edit and submit drafts and submitted requests only while the call is open to them; accepted and confirmed requests stay editable afterwards, and rejected and withdrawn ones never are.
