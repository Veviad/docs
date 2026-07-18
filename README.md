# Veviad user handbook and internal runbooks

This repository powers the authenticated documentation at `docs.veviad.com`.

- **Documentation / Dokumentation** is the English and German Veviad user handbook. It follows common handbook practice: start with product purpose and setup, continue with daily tasks, explain automation and insights, cover administration, and finish with practical help.
- **Internal / Intern** contains bilingual release, upgrade, deployment, search, storage, feedback-ingress, and access-provisioning runbooks for Veviad operators.

Content is written against the current `develop` branch of the Veviad application. English and German pages, navigation entries, icons, links, and screenshots must stay in parity.

## Local preview

From the repository root, run:

```bash
npx mintlify@latest dev
```

The local documentation preview is normally available at `http://localhost:3000`.

## Validation

Run the Mintlify validator before opening a pull request:

```bash
npx mintlify@latest validate
```

Also verify that every MDX image reference resolves, every Documentation group and page has an explicit icon, and neither `public: true` nor an `app.veviad.com` navbar CTA has been introduced.

## Screenshots

User-handbook screenshots come from an isolated local Veviad installation with deterministic synthetic machinery data. Desktop captures use 1440×900; the mobile-navigation example uses 390×844. Store English images in `images/screenshots/` and matching German images in `images/screenshots/de/`.

Never commit credentials, API keys, customer data, or screenshots from a customer environment.

## Publishing

Documentation changes are reviewed in GitHub and deployed from `main`. Keep Documentation and Internal authentication-protected, review the rendered diff, and verify representative English, German, and Internal routes after deployment.
