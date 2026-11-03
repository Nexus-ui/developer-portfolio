# PORT-T-003 — Architecture Decisions, Security & Privacy Rules

**Project:** Developer Portfolio & Technical Blog  
**Sprint:** SPR-00 — Discovery & Architecture  
**Epic:** EP-001 — Discovery & Architecture  
**User Story:** PORT-US-001 — Define portfolio requirements and launch criteria  
**Task:** PORT-T-003  
**Priority:** P0  
**Estimate:** 2 hours  
**Status:** Approved  
**Version:** 1.0  
**Date:** 2026-11-03

## 1. Purpose and scope

This document records technical decisions and minimum security and privacy requirements for a public, English-language, dark-first developer portfolio. The site showcases original demonstrative projects across software engineering, Salesforce, and Agentic AI. It is **not** a web app for managing tasks or a public Notion integration. Notion remains a separate, manual personal task tracker.

### Architecture at a glance

- **Source and content:** GitHub repository with Astro application, local Markdown/MDX articles and project case studies.
- **Build:** Astro static output with TypeScript; Tailwind CSS for styling.
- **Hosting:** Cloudflare Workers Static Assets, reached through a `workers.dev` hostname initially and a personal domain at launch.
- **Publishing:** Git-based PR/check/build/deploy workflow.
- **Runtime data:** No database, authentication or personal-data collection in MVP.
- **Future AI demos:** Separate systems with their own architecture and security review; the portfolio links to them or embeds safe public demos only after approval.

## 2. Architecture Decision Records

Each decision is **Proposed** until the project owner approves this task. Changes after acceptance require a new ADR or an explicit amendment.

### ADR-001 — Static-first generation

**Decision:** Pre-render all portfolio pages into static HTML/CSS/JS at build time. Avoid server-side rendering and bespoke backend endpoints in MVP.

**Context / rationale:** Project listings, case studies and blog posts change only when the author publishes content. Static output minimizes operational cost, attack surface, complexity and client-side JavaScript.

**Consequence / trade-off:** Dynamic user-specific features are postponed. Revisit only if a concrete feature requires server-side behavior.

### ADR-002 — Astro + TypeScript

**Decision:** Use Astro for routing and content-driven rendering and TypeScript for application code. Enable strict type checking where practical.

**Rationale:** Astro is suited to content-oriented sites with selective client-side interactivity.

**Consequence:** Framework integrations and client-side islands must justify their runtime cost.

### ADR-003 — Tailwind CSS and dark-first design

**Decision:** Use Tailwind CSS with reusable UI components, design tokens and semantic markup. Dark-first styling must preserve contrast, readability, keyboard navigation and responsive layouts.

**Consequence:** Avoid one-off visual styles and inaccessible color-only state indicators.

### ADR-004 — Cloudflare Workers Static Assets

**Decision:** Deploy the **static `dist/` output** through Cloudflare Workers using a Wrangler `assets.directory` configuration. Do **not** add a Worker entrypoint or Astro Cloudflare SSR adapter for MVP.

**Rationale:** Cloudflare's Astro guidance supports serving an entirely pre-rendered Astro website as static assets with no Worker code for SSR.

**Consequence:** Cloudflare runtime bindings are not available within pre-rendered pages at request time. If future functionality needs API secrets or request-time processing, create an explicit new design and add the appropriate runtime/adapter then.

### ADR-005 — GitHub as the source of truth

**Decision:** Use GitHub for source code, content, issues as needed and pull requests. `main` represents releasable source. Validate changes before merge.

**Consequence:** The portfolio can be fully rebuilt from the repository. Notion status does not affect production builds.

### ADR-006 — Local Markdown/MDX content

**Decision:** Store blog articles and case studies in Astro Content Collections, defined in `src/content.config.ts` using a filesystem loader and validated metadata schemas.

**Rationale:** Structured content, type safety, reviewable diffs, no CMS dependency.

**Consequence:** Publishing is developer-oriented; a graphical CMS is out of MVP scope.

### ADR-007 — No database in MVP

**Decision:** Do not add SQL/NoSQL databases, KV storage or user accounts for the public portfolio.

**Rationale:** There is no data-persistence requirement in the approved MVP.

**Revisit when:** A validated feature explicitly needs stored server-side state.

### ADR-008 — No public authentication

**Decision:** All published content is publicly accessible and requires no login.

**Consequence:** Draft/private content must not be emitted into the public build at all; hiding a link or route is not access control.

### ADR-009 — English-first content

**Decision:** Use English for visible copy, URLs and documentation intended for visitors. Internationalization is a future option, not part of MVP.

### ADR-010 — Privacy-first, minimal processing

**Decision:** Avoid collecting visitor personal information in MVP. Provide email and professional profile links; no embedded contact form, tracking pixel, newsletter, comments or analytics script by default.

**Consequence:** If analytics or forms are added later, review provider behavior, disclosures and any applicable legal obligations first.

## 3. Security controls

### SEC-01 — Secrets and credentials

- Never put API keys, tokens, passwords or Salesforce credentials in source, MDX, static assets, commits, screenshots or logs.
- Add `.env*` and `.dev.vars*` to `.gitignore` **with carefully chosen exceptions only for non-secret example templates** (e.g., `.env.example` containing placeholders).
- Never place secrets in `PUBLIC_` environment variables or any value bundled into client-side code.
- If a future Cloudflare Worker requires credentials, use Cloudflare encrypted secrets or an appropriate secrets store, never Wrangler plaintext `vars`.
- Review changes for leaked secrets before committing; revoke/rotate any credential accidentally exposed, including those in git history.

### SEC-02 — Repository and supply-chain hygiene

- Enable multi-factor authentication on source/hosting accounts.
- Commit a dependency lockfile and review dependency changes.
- Run package audit / dependency scanning as appropriate; triage high-severity findings before release.
- Give CI deployment tokens minimal required permissions and keep them protected.
- Require successful build and automated checks before deployment to production.

### SEC-03 — Browser-facing security

- Prefer native Astro rendering and safe escaping; never directly inject untrusted HTML without explicit sanitization and review.
- Avoid third-party scripts by default. Vet any script/iframe added later.
- Enable HTTPS and consider HSTS after verifying domain and subdomains.
- Establish a practical Content Security Policy during implementation, testing necessary resources before enforcement; add other suitable security headers according to hosting configuration.
- Validate external links and use `rel="noopener noreferrer"` where opening new tabs with `target="_blank"`.

### SEC-04 — Showcase isolation

- Salesforce demonstrations must use synthetic data and a purpose-built development/scratch environment, never employer credentials or customer records.
- AI demos with model APIs must not expose provider keys in browser code. Run server-side with rate limiting, usage caps and abuse controls **in a separate reviewed deployment**, or share recorded walkthroughs instead.
- Do not embed publicly writable or cost-generating functionality in MVP.

## 4. Privacy and content boundaries

### PRIV-01 — Data minimization

- Collect no personal information from visitors in MVP. `mailto:` links and external profile links are acceptable; they do not create a portfolio-controlled visitor database.
- Do not add analytics, consent banners or cookies merely for appearance. If a service is introduced, inventory its storage/processing behavior first.

### PRIV-02 — Transparency

- Clearly identify third-party destinations (GitHub, LinkedIn and demos).
- At public launch, review privacy/cookie disclosures applicable to the actual services and jurisdiction in use; avoid claiming compliance solely because the site is static.

### PRIV-03 — Ownership, confidentiality, authenticity

- Publish original demonstrative work or materials for which rights and permissions are confirmed.
- No employer/customer source code, proprietary diagrams, confidential architecture, production screenshots or real user data.
- Label synthetic data, conceptual designs and measured outcomes appropriately; do not fabricate production-impact metrics.
- Remove secrets/identifiers from screenshots, logs and recorded demos before publication.

### PRIV-04 — Safe publication of drafts

- Filter draft content out of the production static build, including route generation, project index, search index, sitemap and RSS if added later.
- Do not treat `robots.txt` or a hidden URL as security controls.

## 5. Minimum review checklist (for future Definition of Done)

- [ ] Static build succeeds without a database, SSR adapter or runtime secrets.
- [ ] All relevant pages and assets are generated from version-controlled content.
- [ ] Type checks, lint checks and selected tests pass in CI.
- [ ] Sensitive files are ignored by git and no real secrets are committed.
- [ ] Demo and case study content uses original/synthetic materials with no confidential data.
- [ ] Draft content is excluded from public build outputs.
- [ ] HTTPS and external links have been verified.
- [ ] Dependencies and third-party scripts have been reviewed.
- [ ] Responsive and keyboard-navigation smoke checks pass.
- [ ] Any future telemetry/form/API change triggers a security/privacy ADR review.

## 6. Open decisions and change control

1. **Domain and registrar:** choose before public launch; no blocker for initial Workers deployment.
2. **Analytics:** deferred until post-MVP; evaluate privacy and usefulness first.
3. **Security header policy:** implement and test on Cloudflare during quality sprint.
4. **Demo hosting:** separate architecture decision for each dynamic Agentic AI or Salesforce showcase.
5. **Deployment workflow:** choose Cloudflare Workers Builds or GitHub Actions implementation during SPR-01, with branch checks and protected credentials.

## 7. Acceptance criteria for PORT-T-003

- [x] Static-first architectural decisions recorded with rationale and consequences.
- [x] Source control, content, hosting and out-of-scope components documented.
- [x] Handling rules for credentials, visitor data, drafts and confidential content documented.
- [x] Security checks and conditions for revisiting decisions documented.
- [ ] Owner reviews and accepts this document.
- [ ] Approved document is committed to the GitHub repository during repository setup.

**Status note:** Creation of this file is not proof of deployment, compliance or implementation. Security controls are commitments for future tasks and must be tested as work progresses.

## 8. Primary technical references

- Cloudflare Workers — Astro: https://developers.cloudflare.com/workers/framework-guides/web-apps/astro/
- Cloudflare Workers — Secrets: https://developers.cloudflare.com/workers/configuration/secrets/
- Cloudflare Workers — Environment Variables: https://developers.cloudflare.com/workers/configuration/environment-variables/
- Astro — Content Collections: https://docs.astro.build/guides/content-collections/
