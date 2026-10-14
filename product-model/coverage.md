---
scope: 'The eventyay-exhibition plugin at 29f5d66b59678deb6d04bcd5c5fb17d903a84688: models, views, forms, API, email, signals, templates and scripts.'
method: Static reading of the source, templates, tests and README; nothing was run.
covered:
- description: Data, state flow and the logged changes of requests, profiles, groups, fields, leads, vouchers, devices and emails.
  paths:
  - exhibition/models.py
- description: Back-office, public and applicant views, the personal dashboard pages and their forms and filters.
  paths:
  - exhibition/views.py
  - exhibition/dashboard.py
  - exhibition/forms.py
  - exhibition/filters.py
  - exhibition/urls.py
  - exhibition/social_links.py
- description: Profile creation from requests, voucher pools, devices, attendee data and account matching.
  paths:
  - exhibition/utils.py
- description: Email templates, queuing, sending, placeholders and the scheduled sending task.
  paths:
  - exhibition/mail.py
  - exhibition/tasks.py
  - exhibition/templatetags/
- description: The exhibitor API and the organizer API's exhibitors endpoint.
  paths:
  - exhibition/api.py
- description: Navigation, front page sponsors, menus, placeholders, history labels and deletion clean-up hooks.
  paths:
  - exhibition/signals.py
  - exhibition/apps.py
- description: Page templates and the scripts behind reordering, request actions, the message center and the forms.
  paths:
  - exhibition/templates/
  - exhibition/static/exhibition/js/
exclusions:
- description: Database migrations, including the one-off data backfills.
  paths:
  - exhibition/migrations/
- description: Translations of the interface texts.
  paths:
  - exhibition/locale/
  - .update-locales.sh
  - Makefile
- description: Stylesheets.
  paths:
  - exhibition/static/exhibition/css/
- description: The test suite.
  paths:
  - tests/
- description: Packaging, continuous integration and repository tooling.
  paths:
  - .github/
  - pyproject.toml
  - uv.lock
  - MANIFEST.in
  - .pre-commit-config.yaml
  - .gitignore
  - exhibition/__init__.py
unmapped:
- description: The copy-key endpoint behind each organization row's Copy button; the keys are modelled through their CSV download.
  paths:
  - exhibition/views.py
- description: The permanent redirects from the old call proposals addresses to the request addresses; they carry no behavior of their own.
  paths:
  - exhibition/urls.py
- description: The log-in and registration links from the call page to the request form; pdd-kit refuses a Journey whose person logs in partway.
  paths:
  - exhibition/templates/exhibitors/public_call.html
- description: The Internal notes field of the organization editor, which nothing keeps (reported as a bug, not modelled).
  paths:
  - exhibition/forms.py
limitations: []
---

# Coverage
