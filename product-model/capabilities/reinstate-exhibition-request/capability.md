---
availability:
- place: event-website::signed-in
domain: call-for-exhibitors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestReinstateView
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
---

# Reinstate a request

An applicant puts a request they withdrew back up for review.
