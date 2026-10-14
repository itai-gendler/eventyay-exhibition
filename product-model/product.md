---
id: eventyay-exhibition
summary: 'Exhibitors and sponsors for eventyay events: a call for exhibitors with a configurable form, request review, public exhibitor pages, sponsor tiers, vouchers and lead scanning.'
category: event-management
tags:
- events
- exhibitors
- sponsors
- lead-scanning
- eventyay-plugin
authors:
- name: FOSSASIA
  url: https://github.com/fossasia/eventyay-exhibition
license: Apache-2.0
languages:
- en
- ar
- bn
- de
- es
- fr
- hi
- pt-BR
- ru
- ur
- zh-Hans
limitations:
- 'Applying needs an eventyay account: the call for exhibitors takes requests only from people who are logged in.'
- Every new request is a request to exhibit; whether the organization also sponsors, or only sponsors, is decided by the organizers when they review it.
- Emails the organizers trigger (acceptance, rejection, lead scanning access, vouchers, profile invitations) wait in the outbox until someone sends them; only the applicant's submission confirmation goes out at once.
- 'Vouchers, orders and attendee details stay in the event''s ticket shop: organizations receive codes from pools the organizers create there, and see only the attendee details the organizers choose to share.'
- Leads are scanned with a separate lead scanning app, which the exhibition serves through its API with each organization's access key and device setup tokens.
references:
- kind: doc
  role: intent
  target: README.rst
  title: Eventyay Exhibition README
- kind: code
  role: context
  target: exhibition/apps.py
---

# Eventyay Exhibition

Eventyay Exhibition adds exhibitors and sponsors to an eventyay event. Organizers publish a call for exhibitors with a form of standard fields and custom fields, review the requests that come in, and turn accepted ones into organization profiles; they can also add exhibitors and sponsors by hand. Profiles appear on the event website's Exhibition page and, grouped into sponsor tiers, on its front page once the organizers publish them. Each organization can receive ticket vouchers to hand out and see who redeemed them, and exhibitors scan attendee badges at their booth with the lead scanning app. A message center keeps every email to applicants and organizations, from templates or written by hand, for the organizers to review and send, and applicants follow their requests and profiles in My Exhibitions.

## Intent

In the project's words: "Eventyay Exhibition is a plugin for eventyay that adds exhibitor, sponsor, exhibition booth, proposal, and lead-scanning features to events." It lets organizers "manage exhibitors and sponsors, publish public exhibitor pages, collect exhibitor and sponsor applications, configure custom application questions, and provide exhibitors with access to lead scanning functionality."
