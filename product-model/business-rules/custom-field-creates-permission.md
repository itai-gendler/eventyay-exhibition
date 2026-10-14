---
appliesTo:
- type: entity
  id: custom-field
  effect: creates
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionListView
---

# Only organizers add custom fields

Organizers add the custom fields of the exhibitor form.
