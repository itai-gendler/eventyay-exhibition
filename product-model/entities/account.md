---
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#verified_emails
- kind: code
  role: implementation
  target: exhibition/mail.py#recipient_locale
---

# Account

The eventyay account a person logs in with. The exhibition reads it; the account itself is kept by eventyay.

## Information kept

- **Name** — the person's name, shown to reviewers as the submitter
- **Email** — the login address; it receives request emails when the request has no contact email
- **Verified email addresses** — the addresses the person has confirmed; one matching an organizer-added profile opens that profile in My Exhibitions
- **Preferred language** — the language request emails are written in for this person
