---
appliesTo:
- type: entity
  id: exhibition-request
  effect: creates
permits:
- actors:
  - applicant
  when:
  - entity: event
    fact: Call open
    is: 'Yes'
- actors:
  - applicant
  when:
  - entity: event
    fact: Call enabled
    is: 'On'
  - entity: event
    fact: Private call
    is: 'On'
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestCreateView
- kind: code
  role: implementation
  target: exhibition/views.py#PublicCallEnabledMixin
---

# Applicants send requests while the call is open, or through a private call's secret link

A logged-in applicant creates a request, submitted or as a draft, while the call is enabled and its deadline has not passed. A private call takes requests only from those who came through its current secret link, and from them also after the deadline.
