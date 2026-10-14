---
availability:
- place: organizer-backend
domain: exhibition-requests
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestListView
- kind: code
  role: implementation
  target: exhibition/filters.py#RequestFilterForm
---

# Browse exhibition requests

The organizers' list of an event's exhibition requests, newest change first, with search, state and type filters, sorting, and the decisions open on each row.
