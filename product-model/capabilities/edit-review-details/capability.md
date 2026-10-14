---
availability:
- place: organizer-backend
domain: exhibition-requests
references:
- kind: code
  role: implementation
  target: exhibition/views.py#RequestDetailView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestReviewForm
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestReviewNotesForm
---

# Edit review details

On a request's review page the deciding organizers set what it will be approved as: exhibitor, sponsor or both, the sponsor group, the booth ID and booth name. Everyone reviewing keeps internal review notes.
