---
availability:
- place: event-website::signed-in
domain: call-for-exhibitors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestEditView
- kind: code
  role: implementation
  target: exhibition/utils.py#sync_exhibitor_from_request
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestForm
---

# Edit a request

An applicant changes a request they sent: while it is a draft or submitted, as long as the call is open; once accepted or confirmed, at any time, with the organization name locked. Changes after acceptance are carried to the organization profile and shown to the organizers against what was accepted.
