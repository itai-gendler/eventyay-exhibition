---
availability:
- place: event-website::public
- place: event-website::signed-in
domain: exhibition
references:
- kind: code
  role: implementation
  target: exhibition/views.py#PublicExhibitorDetailView
- kind: code
  role: implementation
  target: exhibition/utils.py#public_exhibitor_sessions
- kind: code
  role: implementation
  target: exhibition/utils.py#build_exhibitor_video_embed
---

# View an exhibitor

An exhibitor's public page shows its banner, logo, name, description, links, video, slides and the related sessions on the published schedule, with Previous and Next stepping through the list the visitor came from.
