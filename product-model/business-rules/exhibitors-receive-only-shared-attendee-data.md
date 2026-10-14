---
appliesTo:
- type: capability
  id: scan-lead
- type: capability
  id: browse-voucher-redemptions
- type: capability
  id: download-voucher-redemptions
references:
- kind: code
  role: implementation
  target: exhibition/api.py#get_allowed_attendee_data
- kind: code
  role: implementation
  target: exhibition/utils.py#attendee_field_specs
---

# Exhibitors receive only the attendee details the event shares

Lead scans and voucher redemptions carry only the attendee details the organizers chose under Data access; a lead keeps the details shared when it was scanned.
