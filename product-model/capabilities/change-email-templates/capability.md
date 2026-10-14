---
availability:
- place: organizer-backend
domain: email-templates
references:
- kind: code
  role: implementation
  target: exhibition/views.py#EmailTemplatesView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionMailTemplatesForm
- kind: code
  role: implementation
  target: exhibition/views.py#EmailTemplatePreviewView
- kind: code
  role: implementation
  target: exhibition/mail.py#DEFAULT_TEMPLATE_SOURCES
---

# Change the email templates

Organizers word each email the exhibition sends, per language: the request confirmation, the organizers' notification, acceptance, rejection, the lead scanning access email, vouchers, the profile invitation and the request for more information, and the custom templates. A preview fills the placeholders with samples.
