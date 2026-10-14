---
appliesTo:
- type: capability
  id: submit-exhibition-request
- type: capability
  id: withdraw-exhibition-request
- type: capability
  id: reinstate-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/mail.py#send_request_organizer_emails
---

# Request teams are told when an applicant submits, withdraws or reinstates

Members of teams that may change exhibition requests or review them are emailed; when there are none, members of teams that may change the event's settings are.
