---
kind: alternative
routes:
  web: Web
steps:
- text: The Exhibitor contact opens the profile from My Exhibitions
  kind: actor
  actor: exhibitor-contact
  entities:
  - entity: organization-profile
    effect: reads
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
  contexts:
    web:
      place: event-website::signed-in::profile-editor
- text: The Exhibitor contact fills in the description, links, logo, banner and booth name and saves
  kind: actor
  actor: exhibitor-contact
  entities:
  - entity: organization-profile
    effect: changes
    facts:
    - Description
    - Website
    - Logo
    - Banner
    - Booth name
    - Social media links
  contexts:
    web:
      place: event-website::signed-in::profile-editor
- text: The Product says the changes have been saved and shows My Exhibitions
  kind: product
  actor: exhibitor-contact
  entities: []
  contexts:
    web:
      place: event-website::signed-in::my-exhibitions
---

# Complete an organizer-added profile

## Trigger

The contact of a profile the organizers added follows the invitation and opens it in My Exhibitions.

## Outcome

The public details are saved; the organizers' settings are untouched.

## Edge cases

- Profiles approved through a request are changed through the request instead.
- An inactive profile, or one whose email no verified address of the account matches, cannot be opened.
