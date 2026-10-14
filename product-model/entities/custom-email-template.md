---
domain: email-templates
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionCustomEmailTemplate
---

# Custom email template

A named subject and body the organizers keep for composing emails.

## Information kept

- **Name** — the template's name
- **Subject** — per language
- **Body** — per language, with placeholders
