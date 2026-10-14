---
domain: exhibitor-form
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionQuestion
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionQuestionForm
---

# Custom field

A question the organizers add to the exhibitor form, beside its standard fields.

## Information kept

- **Question** — the field's label, per language
- **Type** — number, one-line or multiline text, URL, email, confirm checkbox, choose one (radio or dropdown), choose several, file upload, date, time, date and time, country or phone number
- **Help text** — shown below the field
- **Options** — the answers to choose from, for the choice types
- **Required** — whether an answer is needed to submit
- **Active** — whether the form asks it
- **Position** — its place among all fields of the form
- **Depends on** — another checkbox or choice field and the values of it that show this field
