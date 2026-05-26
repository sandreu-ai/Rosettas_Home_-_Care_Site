# Hermes Takeover Plan — Rosetta's Home & Care Site

Date: 2026-05-23

## Verified local project
- Local path: `/home/sandreu/rosettas-home-care-redesign`
- Package type: static HTML/CSS/JS prototype
- Main page: `index.html`
- Assets: `assets/`
- Source zip: `/home/sandreu/rosettas-home-care-redesign.zip`
- Git status: not currently a git repository locally; no remote found.

## Related GHL location
- Business/location: Rosetta's Home and Care
- GHL Location ID: `FVa10mT06tUg01ylJdgk`
- Intake form: `Rosetta's Home Care - Free Consultation Request`
- Intake form ID: `iUswI1hsIBB39NxcWbYG`
- Public form link: `https://api.leadconnectorhq.com/widget/form/iUswI1hsIBB39NxcWbYG`
- Calendar: `Free Consultation`
- Calendar ID: `648cmOCtOjjeFrr9ZRJf`
- Public booking link: `https://api.leadconnectorhq.com/widget/booking/648cmOCtOjjeFrr9ZRJf`
- Pipeline: `Home Care Leads`
- Pipeline ID: `pBimdNHjV74ReFihJjR0`

## Current integration state
- The page now embeds the official GHL intake form iframe for `Rosetta's Home Care - Free Consultation Request`.
- The old local demo form and demo toast handler were removed.
- A secondary Free Consultation booking link is present in the contact panel.
- The LeadConnector form embed script is loaded from `https://link.msgsndr.com/js/form_embed.js`.

## Drift / issues to fix before launch
- `tel:` links were corrected to `tel:+19728787440`.
- Public email was corrected to `admin@rosettahc.com`.
- Public website/domain references were corrected to `rosettashomecare.com`.
- Phone/SMS is not fully live in GHL: no assigned/provisioned SMS-capable number was returned in the last audit, and A2P/10DLC remains pending.

## Safe GHL integration path
1. Replace the local demo form with the GHL intake form embed, or wire the existing custom form to a backend/serverless endpoint that posts into GHL.
2. For fastest safe launch, use the official GHL iframe embed:

```html
<iframe src="https://api.leadconnectorhq.com/widget/form/iUswI1hsIBB39NxcWbYG" style="width:100%;height:100%;border:none;border-radius:3px" id="inline-iUswI1hsIBB39NxcWbYG" data-layout="1" data-trigger-type="alwaysShow" data-trigger-value="" data-activation-type="alwaysActivated" data-activation-value="" data-deactivation-type="neverDeactivate" data-deactivation-value="" data-form-name="Rosetta's Home Care - Free Consultation Request" data-form-id="iUswI1hsIBB39NxcWbYG" title="Rosetta's Home Care - Free Consultation Request"></iframe>
<script src="https://link.msgsndr.com/js/form_embed.js"></script>
```

3. Add the booking link as a secondary CTA: `https://api.leadconnectorhq.com/widget/booking/648cmOCtOjjeFrr9ZRJf`.
4. Keep SMS claims conservative until A2P and an assigned number are verified.
5. Test publicly after deployment: submit controlled test lead, verify contact, fields, opportunity, email response, and workflow path in GHL.

## Privacy / safety
- Do not store CRM contacts, raw submissions, cookies, tokens, or GHL auth material in the repo.
- Use test contacts only for QA.
- No fake reviews, invented licenses, 24/7 claims, insurance claims, or medical/emergency promises.
