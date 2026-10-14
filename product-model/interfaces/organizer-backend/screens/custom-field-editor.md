---
entities:
- entity: custom-field
  shows:
  - Question
  - Depends on
  collects:
  - Question
  - Type
  - Help text
  - Options
  - Required
  - Active
  - Position
  - Depends on
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionEditView
---

# Custom field editor

Adding, changing or deleting one custom field.
