---
availability:
- place: organizer-backend
domain: exhibitor-form
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionListView
- kind: code
  role: implementation
  target: exhibition/models.py#REQUEST_DEFAULT_FIELDS
---

# Change the exhibitor form

Organizers choose which standard fields and custom fields the exhibitor form asks and which are required. The organization name, logo and banner are always asked and required.
