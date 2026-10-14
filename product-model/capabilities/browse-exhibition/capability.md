---
availability:
- place: event-website::public
- place: event-website::signed-in
domain: exhibition
references:
- kind: code
  role: implementation
  target: exhibition/views.py#PublicExhibitorListView
- kind: code
  role: implementation
  target: exhibition/utils.py#public_exhibitors_queryset
- kind: code
  role: implementation
  target: exhibition/filters.py#PublicExhibitorFilterForm
- kind: code
  role: implementation
  target: exhibition/signals.py#exhibition_presale_nav_tab
---

# Browse exhibitors

The Exhibition page of the event website lists the published exhibitors that have a logo and a banner, in the organizers' order, with a search and a sponsor group filter. Organizers can preview it with the approved exhibitors that are not published yet.
