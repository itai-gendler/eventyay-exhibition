---
domain: exhibition-requests
relations:
- entity: queued-email
  verb: receives
  cardinality: one-to-many
- entity: request-history
  verb: records
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequest
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitionRequestState
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitionRequestForm
---

# Exhibition request

An organization's application to exhibit at an event, sent through the call for exhibitors and decided by the organizers. Each request has its own code and belongs to the applicant who sent it.

## Information kept

- **Code** — the request's own twelve-character code, used in its links
- **Organization name** — the organization applying, in the language the form was filled in; locked once accepted
- **Description** — the organization's description
- **Language** — the language the applicant filled the form in; name, description and booth name are kept per language
- **Contact email** — where request emails go; the applicant's login email when empty
- **Website** — the organization's website
- **Contact page URL** — the organization's contact page
- **Video URL** — a promotional video
- **Slides** — promotional slides, an uploaded PDF or a link to one
- **Logo** — the organization's logo image
- **Banner** — the exhibition banner image
- **Booth name** — the booth name the applicant prefers, which reviewers may change
- **Message to the organizers** — a note from the applicant
- **Social media links** — links to the organization's social media profiles, each with its network
- **Extra links** — further labelled links
- **Answers** — the applicant's answers to the custom fields, including uploaded files
- **Exhibitor** — whether the request is approved as an exhibitor; every new request starts as one
- **Sponsor** — whether the request is approved as a sponsor
- **Sponsor group** — the sponsor group the request is approved into
- **Booth ID** — the booth the request is given
- **Internal review notes** — notes the reviewers keep, never shown to the applicant
- **Submitted at** — when it was first submitted
- **Last updated** — when it last changed
- **Profile at acceptance** — the applicant's own fields and answers as they were when it was accepted
- **Edited after acceptance** — when the applicant last changed it after acceptance

## States

### Draft

Saved by the applicant without submitting; only the organization name is required.

### Submitted

Waiting for a decision.

### Accepted

Approved: its organization profile exists and is active; the applicant is asked to confirm.

### Confirmed

Accepted, and the applicant has confirmed taking part; it behaves like an accepted request.

### Rejected

Declined; its organization profile, if any, is inactive.

### Withdrawn

Taken back by the applicant or the organizers; its organization profile, if any, is inactive.
