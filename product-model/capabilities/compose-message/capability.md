---
availability:
- place: organizer-backend
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailComposeView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionComposeForm
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_compose_emails
- kind: code
  role: implementation
  target: exhibition/mail.py#compose_recipients
---

# Compose an email

Request managers and reviewers write one message to the applicants of a chosen state, type and sponsor group, or to chosen organizations including the profiles organizers added. It is sent at once, scheduled, or kept in the outbox; each recipient gets it in their language with the placeholders filled in. From a request's review page it goes to that applicant alone.
