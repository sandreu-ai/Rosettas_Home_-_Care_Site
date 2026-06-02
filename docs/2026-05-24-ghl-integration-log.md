# Rosetta's Home & Care — GHL Integration Log

Date: 2026-05-24

## Location inspected
- Local static site: `/home/sandreu/rosettas-home-care-redesign`
- Related GHL location from takeover docs: Rosetta's Home and Care (`FVa10mT06tUg01ylJdgk`)
- Current GHL chat widget: `6a15c7f7c10806bf190a537f`
- GHL calendar: `Free Consultation` (`648cmOCtOjjeFrr9ZRJf`)

## Changes made
- Corrected public email to `admin@rosettahc.com`.
- Corrected public site/domain references to `rosettashomecare.com`.
- A2P update replaced the embedded GHL/LeadConnector form iframe with the official chat widget and removed public form/booking links from the homepage.
- Removed the demo-only submit handler/toast.
- Added the LeadConnector chat widget script.
- Removed booking/form links from the chat-widget homepage for A2P compliance.
- Corrected public phone `tel:` links to the numeric phone URI.
- Updated `README.md` and `docs/HERMES_TAKEOVER_PLAN.md` to reflect the new integration state.

## Tests performed
- Confirmed the old email/domain/demo form strings are no longer present in the site project.
- Confirmed `index.html` parses successfully with Python HTMLParser.

## Blockers / caveats
- The GHL app/settings page rendered blank in this browser session, so I did not verify or change the live GHL business profile from the authenticated UI.
- SMS remains blocked until GHL phone assignment and A2P/10DLC readiness are verified.

## Privacy / sensitive-data handling
- No CRM contacts, submissions, cookies, tokens, or auth material were copied into the site files.
- No raw GHL credentials or browser storage were inspected or stored.
- Only public business contact details and non-secret GHL embed IDs were documented.

## Next recommended action
- Deploy this static site to the real domain, then run one controlled test submission from `rosettashomecare.com` and verify contact/opportunity/notification behavior inside GHL.
