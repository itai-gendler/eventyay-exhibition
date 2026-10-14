---
actors:
- applicant
- exhibitor-contact
- organizer
access: authenticated
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestListView
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionsView
---

# Logged in

A logged-in person's exhibition requests to the event, their confirmation, and My Exhibitions in their personal dashboard; organizers also preview the exhibition here.
