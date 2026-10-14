---
appliesTo:
- type: capability
  id: assign-vouchers
- type: capability
  id: email-vouchers
references:
- kind: code
  role: implementation
  target: exhibition/utils.py#resolve_voucher_defaults
- kind: code
  role: implementation
  target: exhibition/utils.py#claim_pool_vouchers
---

# Organizations draw vouchers from their pool, all or nothing

Sponsor-only organizations draw from the sponsor pool when one is set, everyone else from the exhibitor pool; the default number is the sponsor group's, else the event's. A request for more codes than the pool has unassigned takes none.
