---
availability:
- place: event-website::signed-in
- place: organizer-backend
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestWithdrawView
- kind: code
  role: implementation
  target: exhibition/views.py#RequestActionView
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
---

# Withdraw a request

An applicant, or the organizers on their behalf, take back a request that is submitted, accepted or confirmed. Its organization profile, if it has one, becomes inactive and leaves the public site.
