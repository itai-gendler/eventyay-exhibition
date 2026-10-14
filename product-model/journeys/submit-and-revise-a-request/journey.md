---
actors:
- applicant
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestCreateView
- kind: code
  role: implementation
  target: exhibition/mail.py#request_public_url
---

# Submit a request and revise it

## Goal

An applicant submits a request and later corrects it from the confirmation email.

## Success criterion

The submitted request carries the applicant's corrections while it waits for review.
