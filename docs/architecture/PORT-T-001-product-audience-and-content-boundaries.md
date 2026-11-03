# PORT-T-001 — Personas, Visitor Journeys & Content Boundaries

**Project:** Developer Portfolio & Technical Blog  
**Epic:** EP-001 — Discovery & Architecture  
**Story:** PORT-US-001 — Define portfolio requirements and launch criteria  
**Sprint:** SPR-00  
**Priority:** P0  
**Estimate:** 2 hours  
**Status:** Approved

## 1. Product positioning

A public, English-language, dark-first engineering portfolio for a **Software Engineer specializing in Salesforce and Agentic AI**. The site will demonstrate capabilities through original showcase projects, technical case studies, source code, and technical writing.

The website is built with Astro, TypeScript, and Tailwind CSS, stored on GitHub, and deployed to Cloudflare Workers. Notion is used separately by the owner for task tracking only; it is **not** a website component, data source, or publishing integration.

## 2. Product objective

Help a recruiter, technical evaluator, or hiring manager quickly understand the developer's strengths, inspect credible implementation evidence, and find a clear route to contact or a résumé.

## 3. Primary personas

### P-01 — Technical Recruiter
- **Goal:** Identify role fit, specialization, technology stack, résumé, and contact details.
- **Needs:** Clear positioning, scannable skill summary, featured projects, downloadable résumé, direct contact links.
- **Pain points:** Excessive jargon, unclear role focus, no contact CTA, unclear personal contribution.
- **Success condition:** Can understand the candidate's profile from the home page and locate the résumé or contact route without searching.

### P-02 — Tech Lead / Software Architect
- **Goal:** Assess implementation quality and engineering judgment.
- **Needs:** Source code, architecture diagrams, technical decisions, tests, trade-offs, limitations, and case studies.
- **Pain points:** Screenshots without code, unsubstantiated claims, unstructured README files, inaccessible repositories.
- **Success condition:** Can open a relevant case study and trace the solution to a source repository or a clearly explained technical artifact.

### P-03 — Engineering Manager
- **Goal:** Evaluate autonomy, problem solving, responsibilities, and evidence of outcomes.
- **Needs:** Context, constraints, contribution, decisions, results or verified observations, and lessons learned.
- **Pain points:** Unclear ownership, inflated claims, missing problem context, vague project value.
- **Success condition:** Can assess the developer's contribution and reach the contact or résumé section.

## 4. Primary visitor journeys

### J-01 — Recruiter journey
1. Open homepage from a CV, LinkedIn profile, or application.
2. Read the professional headline and 1–2-sentence summary.
3. Scan specialties, skills, and featured projects.
4. Open About / Resume or use Contact CTA.

**Expected outcome:** Candidate suitability can be assessed quickly; résumé and contact options are easily discoverable.

### J-02 — Technical evaluation journey
1. Open homepage or project index.
2. Filter by Salesforce, Agentic AI, or Software Engineering.
3. Open a project case study.
4. Review problem, architecture, implementation, trade-offs, testing, and limitations.
5. Open GitHub repository or demo where available.

**Expected outcome:** Technical competence can be evaluated using concrete evidence.

### J-03 — Engineering manager journey
1. Open a featured project.
2. Review problem context, personal role, technical decisions, and outcomes.
3. Review lessons learned and related projects.
4. Go to About, résumé, or Contact.

**Expected outcome:** Manager understands scope of work and evidence of problem-solving ability.

## 5. Functional content boundaries

### In scope
- Homepage with professional positioning and featured work.
- Projects catalog with three primary specialties: Salesforce, Agentic AI, Software Engineering.
- Project case studies covering overview, problem, personal role, architecture, implementation, engineering decisions, testing, results/observations, limitations, lessons learned, and links where available.
- Technical blog in English.
- About, skills, professional résumé and contact links.
- Screenshots, diagrams, code snippets, and links to original public repositories.
- SEO and accessibility essentials.

### Out of scope for initial MVP
- Notion integration, API, database, or publishing pipeline.
- User registration, authentication, or visitor accounts.
- Comments, forums, newsletter, or interactive user profiles.
- Live paid AI demo or hosted backend for showcase applications.
- Admin CMS, database-driven content management, or complex analytics dashboard.
- Multilingual content in the first release.

### Safety, privacy, and integrity rules
- Do not publish client/employer proprietary code, confidential data, internal architecture, credentials, secrets, or identifying customer information without authorization.
- Use original demonstration data and synthetic examples as needed.
- Label showcase projects as demonstrations; do not imply they were delivered to real customers.
- Do not invent usage metrics, performance gains, certifications, job titles, or project outcomes.
- When a result cannot be measured, describe implementation and verifiable observations instead.
- Publish only professional contact information intentionally approved for public display.

## 6. Content ownership and publishing

All content is authored in English and maintained as Markdown/MDX in the GitHub website repository. Project-specific source code may reside in separate public repositories. GitHub and Cloudflare manage source and deployment; Notion remains a separate personal task board.

## 7. Review checklist / Acceptance criteria

- [x] Primary audience and three personas documented.
- [x] Three key visitor journeys documented with outcomes.
- [x] Primary content types defined.
- [x] In-scope and out-of-scope content documented.
- [x] Confidentiality and accuracy boundaries documented.
- [x] Notion explicitly excluded from website architecture.
- [ ] Product owner reviews and accepts assumptions and boundaries.

**Completion rule:** Mark PORT-T-001 as Done in Notion only after the owner has reviewed and approved this document.
