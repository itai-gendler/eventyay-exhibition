---
availability:
- place: organizer-backend
domain: exhibitor-form
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionDefaultFieldEditView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionDefaultFieldForm
---

# Edit a standard field

Organizers give a standard field of the exhibitor form, such as the logo, its own label and help text.
