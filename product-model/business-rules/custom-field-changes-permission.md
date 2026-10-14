---
appliesTo:
- type: entity
  id: custom-field
  effect: changes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionListView
---

# Only organizers change custom fields

Organizers change the custom fields of the exhibitor form.
