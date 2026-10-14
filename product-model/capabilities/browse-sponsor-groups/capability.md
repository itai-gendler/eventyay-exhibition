---
availability:
- place: event-website::public
- place: event-website::signed-in
domain: exhibition
references:
- kind: code
  role: implementation
  target: exhibition/signals.py#presale_supported_by
- kind: code
  role: implementation
  target: exhibition/templates/sponsors/presale_supported_by.html
---

# Browse the sponsors

The event's front page shows, after its own content, each sponsor group the organizers chose for the front page, in level order, with the logos of its published sponsors.
