---
kind: alternative
routes:
  web: Web
steps:
- text: The Applicant enters a search term and picks a sponsor group
  kind: actor
  actor: applicant
  entities:
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: event-website::exhibition
- text: The Product lists the published organization profiles whose name or description matches and that belong to that sponsor group
  kind: product
  actor: applicant
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Description
    - Sponsor group
  - entity: sponsor-group
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: event-website::exhibition
- text: The Applicant reads the matching organization profiles
  kind: actor
  actor: applicant
  entities:
  - entity: organization-profile
    effect: reads
    facts:
    - Name
    - Logo
    - Banner
  contexts:
    web:
      place: event-website::exhibition
---

# Search and filter the exhibitors

## Trigger

A logged-in applicant looks for a particular exhibitor or sponsor tier.

## Outcome

Only the published exhibitors matching the search and the chosen sponsor group are listed; clearing returns the whole list.
