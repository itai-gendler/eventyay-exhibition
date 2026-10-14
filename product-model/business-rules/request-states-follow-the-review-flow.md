---
appliesTo:
- type: entity
  id: exhibition-request
references:
- kind: code
  role: implementation
  target: exhibition/models.py#REQUEST_STATE_TRANSITIONS
- kind: code
  role: implementation
  target: exhibition/models.py#REQUEST_ACTION_SOURCE_STATES
---

# A request moves only along the review flow

A draft can only be submitted. A submitted request is accepted, rejected, withdrawn or taken back to a draft by its applicant. An accepted request is confirmed, rejected, withdrawn or reopened; a confirmed one is moved back to accepted, rejected, withdrawn or reopened. A rejected request is approved or reopened, and a withdrawn one is reinstated or reopened. Confirming and moving back to accepted take effect only if the request is still in the state they start from.
