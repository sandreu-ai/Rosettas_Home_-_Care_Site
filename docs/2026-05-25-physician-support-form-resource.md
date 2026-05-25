# 2026-05-25 — Physician support form printable resource

## Location / project inspected
- Local repo: `/home/sandreu/rosetta_site` → GitHub `sandreu-ai/Rosettas_Home_-_Care_Site`
- Site file updated: `index.html`
- PDF source: local uploaded/cached document `Home_Care_Physician_Support_Form_FINAL.pdf`

## Changes made
- Added `assets/home-care-physician-support-form.pdf`.
- Added a Resources nav item.
- Added a hero CTA: `Print Doctor Form`.
- Added a Resources section with a `Download / Print PDF` button.
- Added a FAQ entry explaining the doctor/insurance use case.
- Added a conservative disclaimer: insurance coverage/reimbursement is decided by the provider and the form is not a guarantee of approval or payment.

## Tests performed
- Confirmed local PDF asset exists and is served as `application/pdf`.
- Confirmed local homepage serves HTTP 200 and contains the new Resources section and PDF link.
- Browser-verified the page shows the Resources nav link, hero print CTA, Resources section, download CTA, and disclaimer.
- Confirmed the repo has no obvious secret-like patterns before attempting Pages publishing.
- Committed and pushed to `origin/main`.

## Blockers
- GitHub Pages is not enabled for this private repo. API returned: `Your current plan does not support GitHub Pages for this repository.`
- GitHub Pages URLs returned 404.
- `rosettashc.com` in `CNAME` did not resolve from this environment.
- `rosettashomecare.com` also did not resolve from this environment at test time.

## Privacy / sensitive-data handling
- No CRM contacts, submissions, cookies, tokens, or customer records were added.
- The PDF appears to be a blank client-facing form/resource, not a completed private record.
- The repo remote/token was not printed or stored in the public doc.

## Next recommended action
- Decide deployment path: either approve making the GitHub repo public/enabling GitHub Pages, or deploy the static site to another host that supports private source repos. After deployment, verify the live homepage and PDF URL, then run one controlled form/lead path if the public site becomes active.
