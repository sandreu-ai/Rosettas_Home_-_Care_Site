# Rosetta's Home & Care — GHL Integration Log

Date: 2026-05-24

## Location inspected
- Local static site: `/home/sandreu/rosettas-home-care-redesign`
- Related GHL location from takeover docs: Rosetta's Home and Care (`FVa10mT06tUg01ylJdgk`)
- GHL form: `Rosetta's Home Care - Free Consultation Request` (`iUswI1hsIBB39NxcWbYG`)
- GHL calendar: `Free Consultation` (`648cmOCtOjjeFrr9ZRJf`)

## Changes made
- Corrected public email to `admin@rosettahc.com`.
- Corrected public site/domain references to `rosettashomecare.com`.
- Replaced the local demo lead form with the official GHL/LeadConnector form iframe.
- Removed the demo-only submit handler/toast.
- Added the LeadConnector embed script.
- Added a secondary Free Consultation booking link in the contact card.
- Corrected public phone `tel:` links to the numeric phone URI.
- Updated `README.md` and `docs/HERMES_TAKEOVER_PLAN.md` to reflect the new integration state.

## Tests performed
- Confirmed the old email/domain/demo form strings are no longer present in the site project.
- Confirmed `index.html` parses successfully with Python HTMLParser.
- Confirmed GHL form URL returns HTTP 200.
- Confirmed GHL booking URL returns HTTP 200.
- Loaded the local page through a local HTTP server and verified the iframe is present in DOM with the correct form ID/source.
- Loaded the GHL form URL directly and verified the form fields render in browser automation.

## Blockers / caveats
- The GHL app/settings page rendered blank in this browser session, so I did not verify or change the live GHL business profile from the authenticated UI.
- In the hosted browser screenshot, the iframe container displayed but the embedded fields appeared blank; the direct GHL form URL rendered correctly. This may be a browser/embedding/rendering issue and should be retested after deployment on the real domain.
- SMS remains blocked until GHL phone assignment and A2P/10DLC readiness are verified.

## Privacy / sensitive-data handling
- No CRM contacts, submissions, cookies, tokens, or auth material were copied into the site files.
- No raw GHL credentials or browser storage were inspected or stored.
- Only public business contact details and non-secret GHL embed IDs were documented.

## Next recommended action
- Deploy this static site to the real domain, then run one controlled test submission from `rosettashomecare.com` and verify contact/opportunity/notification behavior inside GHL.
