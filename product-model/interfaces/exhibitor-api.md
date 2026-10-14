---
type: api
actors:
- lead-scanning-app
entryPoints:
- api: /api/v1/event/{organizer}/{event}/exhibitors/auth
references:
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorAuthView
- kind: code
  role: implementation
  target: exhibition/urls.py
---

# Exhibitor API

The API the lead scanning app calls with an organization's access key: signing in, recording and fetching leads, their notes and tags, and voucher redemptions.
