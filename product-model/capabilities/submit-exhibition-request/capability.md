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
- kind: code
  role: implementation
  target: exhibition/views.py#send_request_confirmation
- kind: code
  role: implementation
  target: exhibition/mail.py#send_request_organizer_emails
---

# Submit a request

A logged-in applicant fills in the exhibitor form, its standard fields and custom fields as the organizers configured them, and submits it for review. The applicant receives a confirmation at once and the event's request reviewers are notified.
