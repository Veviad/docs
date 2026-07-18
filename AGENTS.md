# Veviad documentation instructions

## Purpose

This repository contains two authentication-protected documentation areas:

- **Documentation / Dokumentation** is the task-oriented Veviad user handbook.
- **Internal / Intern** contains operator, deployment, release, and support runbooks.

The user handbook explains the purpose and current behavior of Veviad. It is not a feature catalogue. Organize content around what a user wants to accomplish.

## Product terminology

- Use **asset** for a tracked machine, device, or other managed item.
- Use **People** for workforce directory records that can receive assignments.
- Use **Users** or **application users** for identities that can sign in.
- Use **Actions** for manual, event-driven, and scheduled automation. Do not call the navigation area Workflows.
- Use **Reports** for reusable queries, tables, charts, schedules, runs, and AI summaries.
- Explain that checklists belong to assets and that SCIM has two distinct purposes: application-access provisioning and People-directory provisioning.
- Use the UI labels exactly as they appear in the current `veviad_app/develop` branch.

## Handbook writing standard

- Write in active voice and address the reader as “you” or “Sie”.
- Use sentence case for headings.
- Keep steps short and put UI labels in bold.
- Use code formatting for commands, paths, settings keys, and identifiers.
- A procedural page should include, when relevant: purpose, prerequisites and permissions, steps, expected result, best practices, troubleshooting, and related topics.
- State when an option is permission-dependent, integration-dependent, or unavailable until an administrator configures it.
- Never include credentials, customer data, tokens, private endpoints, or screenshots from a customer environment.

## English and German parity

- Every user-handbook page must have an English and German counterpart with equivalent intent, structure, links, and screenshots.
- Internal release and operations pages must also have English and German parity.
- Add the matching page to both language trees in `docs.json` in the same relative order.
- Every Documentation navigation group and page must define an explicit icon.
- Preserve established URLs where possible; add redirects when a path must change.

## Screenshot conventions

- Capture screenshots only from the isolated local documentation environment using deterministic synthetic machinery data.
- Use light theme, 100% zoom, and 1440×900 for desktop images. Use 390×844 only for mobile-navigation examples.
- Capture matching English and German states and store them under `images/screenshots/` and `images/screenshots/de/` with the same semantic filename.
- Prefer WebP. Crop only when the crop clarifies the documented task; do not hide relevant context.
- Do not expose passwords, API keys, email delivery settings, tenant identifiers, or sensitive user data.
- Replace an existing screenshot in place when the documented state is unchanged. Delete an old image only after confirming that no MDX page references it.

## Content boundaries

- Documentation may describe administrator-facing product screens when end users need them, but it must not expose infrastructure procedures.
- Internal may include commands, configuration tables, deployment evidence, and architecture diagrams. Use screenshots there only for operator-facing UI such as System Information or integration settings.
- Both areas remain authentication-protected. Do not add `public: true` to pages or navigation nodes.

## Validation

Before publishing:

1. Run `npx mintlify@latest validate` from the repository root.
2. Verify English/German page, navigation, icon, link, and screenshot parity.
3. Confirm every referenced image exists and no replacement image is orphaned.
4. Confirm `app.veviad.com` and the **Open Veviad** navbar CTA are absent while the normal `https://veviad.com` link remains.
5. Confirm Documentation and Internal still redirect unauthenticated visitors to sign in.

Use Mintlify MCP for page, navigation, and configuration changes whenever possible. Use GitHub tooling for binary assets and the pull-request workflow.
