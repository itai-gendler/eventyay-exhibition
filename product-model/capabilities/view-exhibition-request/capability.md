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
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/templates/exhibitors/request_detail.html
---

# View an exhibition request

The review page of one request: the submitter, every detail and answer, the internal notes, the emails sent about it, the changes the applicant made since acceptance and, for those who decide requests, its history.
