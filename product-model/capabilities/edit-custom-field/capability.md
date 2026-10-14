---
availability:
- place: organizer-backend
domain: exhibitor-form
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionEditView
- kind: code
  role: implementation
  target: exhibition/models.py#prune_dependency_option
---

# Edit a custom field

Organizers change a custom field's question, type, help text, options, required and active flags or dependency.
