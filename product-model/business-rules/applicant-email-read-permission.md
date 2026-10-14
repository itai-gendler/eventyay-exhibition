---
appliesTo:
- type: entity
  id: exhibition-request
  effect: reads
  facts:
  - Contact email
permits:
- related:
  - verb: owns
    entity: applicant
- actors:
  - organizer
  - request-manager
- actors:
  - request-reviewer
  when:
  - entity: request-reviewer
    fact: Hide applicant emails
    is: 'No'
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#should_hide_applicant_emails
---

# Reviewers whose teams hide applicant emails never see applicants' addresses

Organizers, request managers and the applicant see a request's contact email and the submitter's login email; a request reviewer sees them only unless every reviewer team they belong to hides applicant emails.
