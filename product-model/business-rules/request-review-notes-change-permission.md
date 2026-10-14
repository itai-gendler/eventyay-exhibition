---
appliesTo:
- type: entity
  id: exhibition-request
  effect: changes
  facts:
  - Internal review notes
permits:
- actors:
  - organizer
  - request-manager
  - request-reviewer
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestReviewNotesForm
---

# Only reviewers keep internal review notes

Organizers, request managers and request reviewers write the internal notes; applicants never see them.
