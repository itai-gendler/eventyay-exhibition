---
domain: sponsor-settings
relations:
- entity: organization-profile
  verb: groups
  cardinality: one-to-many
- entity: exhibition-request
  verb: groups
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: exhibition/models.py#SponsorGroup
---

# Sponsor group

A tier of sponsors, such as Gold or Silver, ordered by level.

## Information kept

- **Name** — the group's name, per language
- **Level** — its rank; lower levels come first
- **Show on front page** — whether its published sponsors with a logo appear on the event's front page
- **Vouchers per sponsor** — how many vouchers each organization in the group gets
