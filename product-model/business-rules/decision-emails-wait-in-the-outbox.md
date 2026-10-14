---
appliesTo:
- type: capability
  id: approve-exhibition-request
- type: capability
  id: reject-exhibition-request
- type: capability
  id: add-organization
- type: capability
  id: email-vouchers
- type: capability
  id: add-lead-scanning-devices
references:
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_request_email
- kind: code
  role: implementation
  target: exhibition/views.py#send_request_confirmation
---

# Emails the organizers trigger wait in the outbox

Acceptance, rejection, lead scanning access, voucher and profile invitation emails are placed in the outbox for someone to read and send; only the applicant's submission confirmation is sent at once. Reopening a request sends nothing.
