---
availability:
- place: organizer-backend
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherManageView
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorVoucherBulkSendView
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_voucher_email
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_voucher_emails
---

# Email vouchers

Organizers place a voucher email in the outbox listing every code an organization holds, taking more from the pool first if asked; from the lists, for each selected organization at once.
