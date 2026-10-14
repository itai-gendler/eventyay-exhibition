---
domain: exhibition-requests
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_logentry_display
---

# Request history

The record of what happened to an exhibition request, shown to the organizers on its review page.

## Information kept

- **Who** — the person who acted
- **What happened** — the change, such as approved or changed fields
- **From state** — the state before a state change
- **To state** — the state after it
- **When** — when it happened
