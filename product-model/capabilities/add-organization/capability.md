---
availability:
- place: organizer-backend
- place: organizer-api
domain: exhibitors-and-sponsors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#ExhibitorCreateView
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorInfoForm
- kind: code
  role: implementation
  target: exhibition/views.py#grant_lead_scanning_access
- kind: code
  role: implementation
  target: exhibition/mail.py#queue_exhibitor_profile_email
- kind: code
  role: implementation
  target: exhibition/api.py#ExhibitorInfoSerializer
---

# Add an exhibitor or sponsor

Organizers add an organization profile by hand, as an exhibitor, a sponsor or both. An exhibitor gets a booth ID if none is given, and an invitation to complete the profile in My Exhibitions is placed in the outbox for any exhibitor with an email. Turning on lead scanning or voucher access gives it devices and an access email.
