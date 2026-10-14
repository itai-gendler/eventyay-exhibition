---
availability:
- place: organizer-backend
- place: organizer-api
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorListView
- kind: code
  role: implementation
  target: exhibition/filters.py#ExhibitorFilterForm
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorInfoViewSet
---

# Browse exhibitors and sponsors

The organizers' Exhibitors and Sponsors lists: every organization profile of the event with its booth, publication, access key and voucher email status, the sponsors grouped by sponsor group, with search and filters. The organizer API lists the same profiles.
