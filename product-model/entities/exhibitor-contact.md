---
kind: person
acts: external
relations:
- entity: account
  verb: signs in with
  cardinality: one-to-one
- entity: organization-profile
  verb: manages
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#user_exhibitors
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionsView
---

# Exhibitor contact

The logged-in person who looks after an organization profile in My Exhibitions: the applicant of the request it was approved through, or, for a profile the organizers added, the account whose verified email matches the profile's email.
