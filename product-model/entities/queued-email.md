---
domain: outbox
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionEmailQueue
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_request_email
---

# Queued email

One email to one recipient, written from a template or composed by hand, kept in the message center. A message composed for several recipients is one entry with a row per recipient.

## Information kept

- **Kind** — request confirmation, acceptance, rejection, lead scanning access, vouchers, profile invitation, request for more information, or composed
- **Recipient** — the address it goes to
- **Subject** — the subject
- **Body** — the body, with its placeholders already filled in
- **Language** — the language it was written in
- **Send at** — when it is to be sent by itself
- **Sent at** — when it was sent
- **Attachment** — the voucher list CSV, for voucher emails
- **Batch** — the composed message it belongs to

## States

### In outbox

Waiting for someone to send it.

### Scheduled

Waiting in the outbox for its send time.

### Sent

Sent; it can be read but not changed.
