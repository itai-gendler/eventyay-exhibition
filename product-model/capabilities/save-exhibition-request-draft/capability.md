---
availability:
- place: event-website::signed-in
domain: call-for-exhibitors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestCreateView
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestForm
---

# Save a request as a draft

An applicant saves the exhibitor form without submitting it, to finish later. Only the organization name is needed; a submitted request that is not yet decided can also be taken back to a draft.
