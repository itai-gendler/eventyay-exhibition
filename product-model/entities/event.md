---
relations:
- entity: exhibition-request
  verb: holds
  cardinality: one-to-many
- entity: organization-profile
  verb: holds
  cardinality: one-to-many
- entity: sponsor-group
  verb: holds
  cardinality: one-to-many
- entity: custom-field
  verb: holds
  cardinality: one-to-many
- entity: queued-email
  verb: holds
  cardinality: one-to-many
- entity: custom-email-template
  verb: holds
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitorSettings
- kind: code
  role: implementation
  target: exhibition/mail.py#get_email_template
---

# Event

An eventyay event that uses the exhibition. It keeps the call for exhibitors, the exhibitor form's standard fields, what attendee data exhibitors receive, the voucher and lead-scanning defaults and the email templates.

## Information kept

- **Name** — the event's name, used in every email
- **Call enabled** — whether the call for exhibitors is published
- **Call headline** — the call page's headline, per language; also the label of the call's tab on the event website
- **Call text** — the call page's text, per language
- **Submission deadline** — after it, the call is closed unless the visitor came through the secret link
- **Hide call after deadline** — whether the call page disappears once the deadline has passed
- **Private call** — whether the call can be reached only through the secret link
- **Secret call link** — the link that opens a private call, and lets applicants submit after the deadline
- **Call open** — derived: the call is enabled and its deadline, if any, has not passed
- **Standard fields** — for each standard field of the exhibitor form, whether it is asked, whether it is required, its place in the form and an optional own label and help text
- **Shared attendee data** — which attendee details exhibitors receive from lead scans and voucher redemptions: name and email, and the company, job title, address and custom questions the ticket shop makes required
- **Exhibitor voucher pool** — the voucher tag organizations draw their codes from
- **Sponsor voucher pool** — the voucher tag sponsor-only organizations draw from; empty means the exhibitor pool
- **Vouchers per organization** — how many codes an organization gets when its sponsor group sets none
- **Attach voucher list** — whether the voucher email carries the recipient's codes as a CSV file
- **Devices per profile** — how many lead-scanning devices a profile gets when lead scanning is turned on for it, up to 50; 0 means devices are added by hand
- **Email templates** — the subject and body of each email the exhibition sends, per language, each falling back to its default
- **Content languages** — the languages an applicant can fill in the exhibitor form in
