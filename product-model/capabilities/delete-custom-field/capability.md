---
availability:
- place: organizer-backend
domain: exhibitor-form
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionDeleteView
- kind: code
  role: implementation
  target: exhibition/models.py#clear_dependencies_on
---

# Delete a custom field

Organizers delete a custom field with its answers; fields that depended on it are shown to everyone again.
