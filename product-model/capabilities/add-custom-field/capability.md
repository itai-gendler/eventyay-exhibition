---
availability:
- place: organizer-backend
domain: exhibitor-form
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitionQuestionCreateView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionQuestionForm
- kind: code
  role: implementation
  target: exhibition/forms.py#BaseExhibitionQuestionOptionFormSet
---

# Add a custom field

Organizers add a question to the exhibitor form, of one of fifteen types, optionally shown only when a checkbox or choice field has certain answers.
