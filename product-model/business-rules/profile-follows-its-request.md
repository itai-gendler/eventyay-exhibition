---
appliesTo:
- type: capability
  id: reject-exhibition-request
- type: capability
  id: withdraw-exhibition-request
- type: capability
  id: reopen-exhibition-request
- type: capability
  id: approve-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
---

# A profile is inactive and unpublished whenever its request is not accepted

Rejecting, withdrawing or reopening an accepted or confirmed request makes its profile inactive and takes it off the public site; approving again makes it active without publishing it.

## Rationale

Re-approval would otherwise put a profile back on the public site without an organizer deciding to publish it.
