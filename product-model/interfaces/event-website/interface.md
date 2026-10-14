---
type: web
actors:
- visitor
- applicant
- exhibitor-contact
- organizer
entryPoints:
- web: /{organizer}/{event}/exhibition/
- web: /{organizer}/{event}/exhibition/call/
- web: /common/exhibitions/
references:
- kind: code
  role: implementation
  target: exhibition/urls.py
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_presale_nav_tab
---

# Event website

The event's public website with the exhibition, the sponsors on its front page and the call for exhibitors, and the pages a logged-in person uses there and in their personal dashboard: their exhibition requests and My Exhibitions.
