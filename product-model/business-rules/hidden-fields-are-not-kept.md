---
appliesTo:
- type: capability
  id: submit-exhibition-request
- type: capability
  id: edit-exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionQuestionDependencyMixin
---

# A custom field hidden by another field's answer neither blocks the form nor keeps an answer

A field shown only for certain answers of another field is ignored while those answers are not given; an answer the applicant hid by changing the other field is removed, while one whose other field was deleted or deactivated is kept.
