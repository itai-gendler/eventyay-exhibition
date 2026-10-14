---
availability:
- place: event-website::signed-in
- place: organizer-backend
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestConfirmView
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/views.py#RequestDetailView
---

# Confirm participation

After acceptance, the applicant confirms they will take part, through the link in the acceptance email; organizers can also confirm for them.
