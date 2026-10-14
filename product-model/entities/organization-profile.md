---
domain: exhibitors-and-sponsors
relations:
- entity: exhibition-request
  verb: is approved through
  cardinality: one-to-many
- entity: lead
  verb: collects
  cardinality: one-to-many
- entity: lead-tag
  verb: keeps
  cardinality: one-to-many
- entity: voucher
  verb: holds
  cardinality: one-to-many
- entity: lead-scanning-device
  verb: uses
  cardinality: one-to-many
- entity: queued-email
  verb: receives
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/models.py#ExhibitorInfo
- kind: code
  role: implementation
  target: exhibition/forms.py#ExhibitorInfoForm
---

# Organization profile

An exhibitor, a sponsor, or both, at one event: the profile the public exhibition shows and the organization that gets vouchers and scans leads. It is created when a request is approved, or added by the organizers.

## Information kept

- **Name** — the organization's name, per language
- **Description** — the organization's description, per language
- **Website** — the organization's website
- **Email** — where emails to the organization go; when empty, the address of the request it was approved through
- **Contact page URL** — linked as Get In Touch on the public page
- **Video URL** — a promotional video, embedded when it is a YouTube, Vimeo or video file link
- **Slides** — promotional slides, an uploaded PDF or a link to one
- **Logo** — the logo image
- **Banner** — the exhibition banner, shown complete on the public page
- **Booth name** — the booth's name, per language
- **Social media links** — links to social media profiles, each with its network
- **Extra links** — further labelled links
- **Exhibitor** — whether it exhibits
- **Sponsor** — whether it sponsors
- **Sponsor group** — the sponsor group it belongs to
- **Booth ID** — its booth, unique within the event and generated when an exhibitor has none
- **Access key** — the eight-character key the lead scanning app signs in with
- **Lead scanning** — Can scan attendee badges: whether its staff may scan leads
- **Lead access** — Can view and export collected leads
- **Voucher access** — Can view voucher redemptions
- **Lead scanning behavior** — whether an attendee is one lead across all its devices, or a new lead on each device
- **Related sessions** — accepted sessions of the event shown on its public page
- **Position** — its place in the exhibitors list, and among the sponsors of its group
- **Added by the organizer** — derived: it was added by the organizers rather than approved from a request

## States

### Unpublished

Active but not on the public event website.

### Published

Shown on the public event website.

### Inactive

Hidden because the request it came from was rejected, withdrawn or reopened; it cannot be published or edited by its contact.
