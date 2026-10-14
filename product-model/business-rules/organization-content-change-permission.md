---
appliesTo:
- type: entity
  id: organization-profile
  effect: changes
  facts:
  - Name
  - Description
  - Website
  - Contact page URL
  - Video URL
  - Slides
  - Logo
  - Banner
  - Booth name
  - Social media links
  - Extra links
permits:
- actors:
  - organizer
- related:
  - verb: manages
    entity: exhibitor-contact
  when:
  - fact: Added by the organizer
    is: 'Yes'
  - state: Unpublished
- related:
  - verb: manages
    entity: exhibitor-contact
  when:
  - fact: Added by the organizer
    is: 'Yes'
  - state: Published
- related:
  - verb: is approved through
    entity: exhibition-request
  - verb: owns
    entity: applicant
- actors:
  - request-manager
  when:
  - state: Inactive
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionEditView
- kind: code
  role: implementation
  target: exhibition/utils.py#user_can_edit_profile
- kind: code
  role: implementation
  target: exhibition/utils.py#sync_exhibitor_from_request
---

# Organizers, the profile's contact and its applicant change a profile's public details

Organizers change any profile's public details. The contact of a profile the organizers added changes them while it is active, and the applicant's changes to an accepted request are carried onto its profile. Re-approving a request brings its booth name back to an inactive profile.
