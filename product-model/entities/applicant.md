---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: exhibition-request
  verb: owns
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestCreateView
- kind: code
  role: implementation
  target: exhibition/views.py#UserRequestListView
---

# Applicant

A logged-in person who sends exhibition requests to an event's call for exhibitors and follows them through review.
