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
- Chat widget: LeadConnector/GHL website chat
- Chat widget ID: `6a15c7f7c10806bf190a537f`
- A2P rule: the chat widget is the only online SMS opt-in/contact collection method on pages where it is embedded
- Calendar: `Free Consultation`
- Calendar ID: `648cmOCtOjjeFrr9ZRJf`
- A2P homepage note: do not link/embed appointment forms on pages where the chat widget is embedded unless reviewed separately.
- Pipeline: `Home Care Leads`
- Pipeline ID: `pBimdNHjV74ReFihJjR0`

## Current integration state
- The page now embeds the official GHL intake form iframe for `Rosetta's Home Care - Free Consultation Request`.
- The old local demo form and demo toast handler were removed.
- A secondary Free Consultation booking link is present in the contact panel.
- The LeadConnector chat widget script is loaded from `https://widgets.leadconnectorhq.com/loader.js`.

## Drift / issues to fix before launch
- `tel:` links were corrected to `tel:+19728787440`.
- Public email was corrected to `admin@rosettahc.com`.
- Public website/domain references were corrected to `rosettashomecare.com`.
- Phone/SMS is not fully live in GHL: no assigned/provisioned SMS-capable number was returned in the last audit, and A2P/10DLC remains pending.

## Safe GHL integration path
1. Use the GHL chat widget as the website's online contact/SMS opt-in method on the homepage; do not add embedded forms that collect phone numbers or SMS consent on the same page.
2. For fastest safe launch, use the official GHL iframe embed:

```html
<script src="https://widgets.leadconnectorhq.com/loader.js" data-resources-url="https://widgets.leadconnectorhq.com/chat-widget/loader.js" data-widget-id="6a15c7f7c10806bf190a537f" data-source="WEB_USER"></script>
```

3. Keep CTAs pointed to phone, email, or the chat widget unless a separate non-widget page is created and reviewed for A2P compliance.
4. Keep SMS claims conservative until A2P and an assigned number are verified.
5. Test publicly after deployment: submit controlled test lead, verify contact, fields, opportunity, email response, and workflow path in GHL.

## Privacy / safety
- Do not store CRM contacts, raw submissions, cookies, tokens, or GHL auth material in the repo.
- Use test contacts only for QA.
- No fake reviews, invented licenses, 24/7 claims, insurance claims, or medical/emergency promises.
