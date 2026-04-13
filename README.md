# Ember — Support & Privacy pages

Two static HTML pages to host on GitHub Pages and submit to the App Store.

## Files

- **`index.html`** — Support page (FAQ + troubleshooting + contact)
- **`privacy.html`** — Privacy Policy

Both pages cross-link to each other via a footer nav.

## Deploy to GitHub Pages in 5 minutes

1. **Create a new public repo** on GitHub called `ember-support` (or any name — the repo name becomes part of the URL).
2. **Upload both files** to the repo root. Just drag-and-drop in the GitHub web UI or `git push` them.
3. **Enable Pages**: Repo → Settings → Pages → Source: `Deploy from a branch` → Branch: `main` (or `master`), folder: `/ (root)` → Save.
4. Wait ~1–2 minutes. GitHub will display your live URL at the top of the Pages settings. It'll look like:
   - `https://<your-username>.github.io/ember-support/`
   - Support page: `https://<your-username>.github.io/ember-support/`
   - Privacy page: `https://<your-username>.github.io/ember-support/privacy.html`

## What to paste into App Store Connect

- **Support URL** (required): `https://<your-username>.github.io/ember-support/`
- **Privacy Policy URL** (required): `https://<your-username>.github.io/ember-support/privacy.html`
- **Marketing URL** (optional): leave blank, or reuse the support URL

## Before you submit — things to change

1. **Email address.** Both pages reference `support@emberjournal.app` — either register that domain + email, or swap it for whatever real address you'll monitor. Apple reviewers will email the support address to test it; if it bounces, your review gets delayed.
2. **Effective date on privacy.html.** Currently set to April 13, 2026. Update if submitting on a different date.
3. **Accuracy check on privacy.html.** Read the "Information we do not collect" list carefully. If you end up adding anything that makes a network call — TestFlight telemetry counts, CloudKit sync counts, StoreKit calls to validate purchases count — update the policy before submission. StoreKit/App Store purchase validation is handled by Apple and doesn't usually require disclosure, but anything you add beyond that does.
4. **Optional custom domain.** If you own a domain, GitHub Pages supports custom domains (e.g. `emberjournal.app`). In the repo Settings → Pages → Custom domain, enter your domain and add a CNAME record at your registrar. Cleaner URL, looks more professional on the App Store listing.

## Design notes

- **Dark warm theme** matching the app (charcoal background, cream text, amber ember accent)
- **Instrument Serif** for headlines (closest free Google Fonts analog to SF Pro Serif)
- **Inter** for body copy
- Fully **responsive** — tested at 320px through desktop widths
- **No JavaScript, no tracking, no external resources** other than Google Fonts. The privacy page's claim that "we don't use analytics" applies to the website too
- Native `<details>` elements for FAQ accordions (no framework needed)
