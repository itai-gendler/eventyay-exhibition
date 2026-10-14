---
appliesTo:
- type: entity
  id: custom-field
  effect: removes
permits:
- actors:
  - organizer
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionListView
---

# Only organizers delete custom fields

Organizers delete the custom fields of the exhibitor form.
