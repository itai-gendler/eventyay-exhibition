---
entities:
- entity: event
  shows:
  - Standard fields
  collects:
  - Standard fields
- entity: custom-field
  shows:
  - Question
  - Active
  - Required
  collects:
  - Active
  - Required
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionListView
---

# Exhibitor form

The standard fields and custom fields of the exhibitor form.
