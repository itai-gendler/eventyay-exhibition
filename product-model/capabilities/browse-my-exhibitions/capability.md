---
availability:
- place: event-website::signed-in
domain: my-exhibitions
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionsView
- kind: code
  role: implementation
  target: exhibition/dashboard.py#user_has_exhibitions
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_nav_global
---

# Browse My Exhibitions

In their personal dashboard, a person sees every exhibition they take part in across events: their requests with their state, and the profiles organizers added for their verified email, with links to edit and to their vouchers.
