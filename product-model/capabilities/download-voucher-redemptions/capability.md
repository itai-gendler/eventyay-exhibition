---
availability:
- place: event-website::signed-in
domain: my-exhibitions
references:
- kind: code
  role: implementation
  target: exhibition/dashboard.py#MyExhibitionVouchersView
- kind: code
  role: implementation
  target: exhibition/utils.py#build_voucher_redemption_csv
---

# Download voucher redemptions

The exhibitor contact downloads the redemptions of their organization's vouchers as a CSV with the same columns as the page.
