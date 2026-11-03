# PORT-T-002 — MVP Scope & Measurable Success Criteria

**Project:** Developer Portfolio & Technical Blog  
**Epic:** EP-001 — Discovery & Architecture  
**Story:** PORT-US-001 — Define portfolio requirements and launch criteria  
**Sprint:** SPR-00  
**Priority:** P0  
**Estimate:** 2 hours  
**Status:** Approved  
**Related deliverable:** PORT-T-001 — Personas, Visitor Journeys & Content Boundaries

## 1. Product and MVP definition

An English-language, dark-first engineering portfolio positioning its owner as a **Software Engineer specializing in Salesforce and Agentic AI**. The portfolio uses **Astro, TypeScript, Tailwind CSS, GitHub, and Cloudflare Workers**, with Markdown/MDX for content. Notion is **only an external personal task tracker**; there is no Notion API or site integration.

**Two distinct milestones:**

- **MVP / technical feature-complete (internal milestone):** The site infrastructure, templates, navigation, and quality gates work with representative sample content. This milestone is **not automatically a public launch**.
- **v1.0 / public portfolio launch:** The MVP passes release checks and contains credible, finished original showcase content. Public promotion happens only once the minimum content gate is met.

This distinction prevents publishing a technically polished but empty portfolio.

## 2. MVP scope — Must Have

| ID | Feature | MVP acceptance / observable evidence |
|---|---|---|
| MVP-01 | Site foundation | Astro + TypeScript + Tailwind build locally and in CI; GitHub repository exists. |
| MVP-02 | Hosting and delivery | A Cloudflare Workers preview/production deployment serves the generated static site over HTTPS; Git changes can be deployed repeatably. |
| MVP-03 | Design system and navigation | Consistent dark-first layout, accessible navigation, and responsive header/footer on mobile and desktop. |
| MVP-04 | Homepage | Headline communicates Software Engineer + Salesforce + Agentic AI; links to Projects, Resume, and Contact are discoverable. |
| MVP-05 | Project catalog | Project list displays title, summary, specialization, technologies; filter by Salesforce, Agentic AI, Software Engineering, and All. |
| MVP-06 | Case study template | Reusable project detail route supports problem, role, architecture, implementation, decisions, tests, outcomes/limitations, and optional GitHub/demo links. |
| MVP-07 | Technical blog | Blog list and article template render Markdown/MDX with code syntax highlighting and publication metadata. |
| MVP-08 | About and resume | About/skills overview, downloadable PDF resume (real and reviewed before public launch). |
| MVP-09 | Contact | Working mailto or external professional-profile links; no form/backend required. |
| MVP-10 | Content workflow | New project/article added by Markdown/MDX file + validated frontmatter; draft content excluded from production listings. |
| MVP-11 | SEO essentials | Unique title/description per page, canonical URLs, sitemap, robots policy, and basic social sharing metadata. |
| MVP-12 | Baseline accessibility and quality | Keyboard-accessible navigation, meaningful image alternatives, appropriate contrast and headings; CI build/lint/tests pass. |

Representative internal fixture content can be used to test templates during the MVP phase; it must never masquerade as a finished public project.

## 3. v1.0 public-release content gate

Required **before actively sharing the URL in job applications**:

1. **Three original, functioning demonstrative projects** — one Salesforce, one Agentic AI, one general Software Engineering — each with a complete, honest case study.
2. Each project has a repository or equivalent non-confidential technical evidence (code, architecture, tests); demos are optional.
3. **Two published technical articles** with original, reviewed explanations.
4. Final English copy, accurate personal biography and skills, current résumé PDF, and working professional contact links.
5. No misleading claims about customer usage, impact, metrics, production-readiness, or AI evaluation results.

If the demonstration projects require more effort than initially estimated, expand the content sprints rather than watering down the content gate. A private preview or soft launch can precede v1.0, but must not be called a fully ready professional showcase.

## 4. Should Have — after MVP, subject to capacity

- Dark/light theme toggle (dark-first remains default).
- Project and article search; improved tags and cross-links.
- Privacy-friendly analytics with appropriate disclosure.
- Richer architecture diagrams, including Mermaid when beneficial.
- Additional automated end-to-end test coverage.

## 5. Could Have — future releases

- Interactive Agentic AI demonstrations (only after abuse protection, usage limits, privacy, and cost controls).
- Advanced filters, project timelines, and richer media demos.
- A content-editing interface/CMS, only if Git-based authoring becomes limiting.
- Extended metrics dashboard and optional multilingual version.

## 6. Explicitly out of scope for MVP

- User accounts, login, visitor-specific data, comments, community features.
- Database, content API, bespoke admin backend, or Notion integration.
- Hosted AI inference and chargeable model API calls.
- Newsletter, complex form processing, CRM integration, or tracking without a defined privacy purpose.
- Production deployments of all three showcase applications (code and verified case studies are required for v1.0; live hosted demos are not).
- Invented performance or business-impact claims; confidential company/customer materials.

## 7. Measurable success criteria and verification

| ID | Criterion | Target | Verification | Gate |
|---|---|---|---|---|
| KPI-01 | Positioning clarity | Headline mentions Software Engineer and the two specializations; key CTA visible without complex navigation | Manual homepage review at desktop and mobile widths | MVP |
| KPI-02 | Discoverability of project evidence | From homepage to any featured case study in <=2 clicks; case study provides evidence link when available | Manual navigation checklist | MVP |
| KPI-03 | Functional coverage | All 12 MVP feature requirements meet their acceptance checks | Requirement checklist and review | MVP |
| KPI-04 | Build reliability | Production build and configured CI checks succeed for release commit | GitHub checks and build logs | MVP |
| KPI-05 | Accessibility | Keyboard navigation works; no known critical automated accessibility issues; manual contrast/focus checks complete | Accessibility audit and keyboard smoke test | MVP |
| KPI-06 | Lighthouse performance | >=90 Performance on representative mobile run for Home, Projects, Case Study, Blog | Lighthouse mobile runs on deployed production-like build; record conditions/results | v1.0 |
| KPI-07 | Lighthouse accessibility and SEO | >=90 on Accessibility and SEO on same representative page set | Lighthouse reports plus manual audit (scores do not prove WCAG conformance) | v1.0 |
| KPI-08 | Broken links | Zero known broken internal navigation links and zero broken primary contact/resume links | Automated link check + manual external link sampling | v1.0 |
| KPI-09 | Showcase depth | 3 original demonstrative case studies, one in each specialization | Content inventory and case-study review | v1.0 |
| KPI-10 | Blog depth | At least 2 published reviewed English articles | Published article inventory | v1.0 |
| KPI-11 | Content credibility | Each published case study distinguishes what was implemented, tested, observed, and planned | Editorial checklist per project | v1.0 |
| KPI-12 | Security/privacy | No secrets in committed artifacts; no confidential materials; only necessary personal contact data published | Secret scan, repository review, content sign-off | v1.0 |

**Measurement notes:** Lighthouse scores vary by environment; save the date, URL, device preset, and run output with each measurement. Scores are quality targets, not promises of real-world traffic or job outcomes. We will measure visitor conversion only after traffic and a privacy-respecting measurement method exist.

## 8. MVP exit checklist

- [ ] MVP-01 through MVP-12 verified with evidence.
- [ ] Homepage, Projects, a representative Case Study, Blog, About, Resume, and Contact routes render correctly.
- [ ] Responsive and keyboard checks completed.
- [ ] Cloudflare Workers deployment and rollback procedure documented.
- [ ] Draft/fixture content is clearly separated from real published content.
- [ ] Remaining v1.0 content work is captured in the backlog.

## 9. v1.0 launch checklist

- [ ] MVP exit checklist complete.
- [ ] KPI-06 through KPI-12 verified and evidence retained.
- [ ] Three demonstrative projects and two articles published.
- [ ] Real résumé and contact information approved.
- [ ] Domain and public indexing rules reviewed.
- [ ] Links to portfolio added to professional channels only after release sign-off.

## 10. Acceptance criteria for PORT-T-002

- [x] The internal MVP scope is explicitly defined.
- [x] The v1.0 content/release boundary is explicitly defined.
- [x] Must/Should/Could and out-of-scope items are recorded.
- [x] Success criteria have targets and verification methods.
- [ ] Product owner approves scope and success criteria.

**Decision to approve:** Keep MVP as an internally releasable platform and reserve the *publicly promoted* v1.0 milestone for a portfolio with three credible showcase projects and two technical articles.
