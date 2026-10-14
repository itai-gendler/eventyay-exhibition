---
availability:
- place: organizer-backend
- place: organizer-api
- place: event-website::signed-in
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorEditView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorInfoForm
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionEditView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorSelfEditForm
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorInfoSerializer
---

# Edit an exhibitor or sponsor

Organizers change an organization profile, including the custom field answers of the request it was approved through. The contact of a profile the organizers added completes and maintains its public details in My Exhibitions.
