---
kind: person
acts: external
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#should_hide_applicant_emails
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_access
---

# Request reviewer

A member of an exhibition reviewer team: they read requests, keep internal review notes and use the message center, but do not decide requests.

## Information kept

- **Hide applicant emails** — set on the reviewer's teams; when every reviewer team of the person hides them, applicant email addresses are not shown to them
