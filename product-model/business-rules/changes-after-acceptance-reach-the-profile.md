---
appliesTo:
- type: capability
  id: edit-exhibition-request
- type: capability
  id: view-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#sync_exhibitor_from_request
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
---

# An applicant's changes after acceptance reach the profile and are shown against what was accepted

Editing an accepted request copies the applicant's details onto its organization profile in the request's language, and the review page lists every field changed since acceptance.
