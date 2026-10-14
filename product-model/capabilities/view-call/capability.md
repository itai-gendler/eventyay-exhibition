---
availability:
- place: event-website::public
- place: event-website::signed-in
domain: call-for-exhibitors
references:
- kind: code
  role: implementation
  target: exhibition/views.py#PublicCallView
- kind: code
  role: implementation
  target: exhibition/views.py#PublicCallSecretView
- kind: code
  role: implementation
  target: exhibition/views.py#PublicCallEnabledMixin
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_presale_nav_tab
---

# View the call for exhibitors

The call page shows the call's headline, text and deadline and leads to the request form. A private call opens only through its secret link, which also lets the visitor submit after the deadline.
