---
kind: system
acts: external
references:
- kind: code
  role: implementation
  target: exhibition/api.py#LeadCreateView
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorAuthView
---

# Lead scanning app

The app an exhibitor's staff use at the booth. It calls the exhibitor API with the organization's access key to scan attendee badges, keep notes and tags on leads and fetch leads and voucher redemptions.
