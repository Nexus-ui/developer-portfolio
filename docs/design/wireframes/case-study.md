# Technical Case Study — Wireframe Specification

Task: PORT-T-010
Status: Draft
Page: Technical Case Study
Route: `/projects/[slug]`

## Purpose

Demonstrate engineering skills through a structured description
of a technical project, including architecture, implementation,
decision-making, testing and results.

## Target Users

- Technical recruiters
- Software engineers
- Tech leads and architects
- Engineering managers

## Primary User Goal

Understand the problem solved, evaluate the engineering approach,
and inspect supporting technical evidence.

## Desktop Layout

Reference viewport: 1440px.

### 1. Global Navigation

- Shared site header.
- Navigation links consistent with other pages.
- Accessible breadcrumb navigation.

### 2. Project Hero

Required elements:

- Project title.
- Specialization category.
- Short technical summary.
- Technology badges.
- Developer role and responsibilities.

Optional actions:

- GitHub repository.
- Live demo.
- Technical documentation.

Actions appear only when their destinations are available.

### 3. Project Overview Visual

- Architecture diagram, screenshot or technical illustration.
- Descriptive caption.
- Accessible alternative text.
- Responsive presentation.

### 4. Table of Contents

Desktop:

- Left sidebar with section navigation.
- Sticky positioning when appropriate.
- Active section state as an optional enhancement.

Mobile:

- Compact "Jump to Section" navigation.
- No persistent sidebar.

### 5. Main Content

Recommended sections:

1. Overview
2. Problem & Requirements
3. My Role & Responsibilities
4. System Architecture
5. Implementation
6. Technical Decisions & Trade-offs
7. Testing & Quality
8. Results & Outcomes
9. Challenges & Lessons Learned
10. Resources

Not all sections are mandatory for every project, but a clear
problem, approach, implementation and verification are required.

### 6. Technical Content Components

The template must support:

- Syntax-highlighted code blocks.
- Architecture diagrams.
- Technical screenshots.
- Tables.
- Lists.
- External repository links.
- Inline technical terminology.
- References and documentation.

### 7. Related Projects

- Show relevant projects when available.
- Provide a link back to the complete project catalog.

## Mobile Layout

Reference viewport: 390px.

- Single-column content.
- Hero actions stack or wrap.
- Compact table of contents.
- Diagrams scale within the content width.
- Code blocks scroll horizontally within their own container.
- Tables remain usable without horizontal page overflow.
- Long headings wrap correctly.
- Adequate spacing around technical content.

## Specialization-Specific Sections

### Salesforce

Possible technical evidence:

- Apex architecture.
- Lightning Web Components.
- Flow automation.
- Integration patterns.
- Governor limits.
- Security and sharing.
- Test strategy.

### Agentic AI

Possible technical evidence:

- Agent orchestration.
- Tool calling.
- RAG architecture.
- Model selection.
- Evaluation and guardrails.
- Latency and operating costs.

### Software Engineering

Possible technical evidence:

- API design.
- Database architecture.
- Design patterns.
- Testing.
- CI/CD.
- Security and observability.

## Content Integrity

- Publish only original or authorized material.
- Never expose credentials or confidential customer data.
- Distinguish implemented features from planned improvements.
- Do not invent performance metrics or business outcomes.
- Clearly identify demonstrations and simulated results.

## Accessibility Requirements

- Semantic heading hierarchy.
- Keyboard-accessible table of contents.
- Visible focus indicators.
- Meaningful alternative text.
- Accessible code and diagram descriptions.
- Sufficient text contrast.

## Out of Scope

- User comments.
- User ratings.
- Authentication.
- Community discussions.
- Database-driven project content.

## Review Checklist

- [ ] Desktop layout reviewed.
- [ ] Mobile layout reviewed.
- [ ] Technical content hierarchy approved.
- [ ] Table of contents behavior approved.
- [ ] Code and diagram presentation reviewed.
- [ ] Accessibility requirements reviewed.
- [ ] Content confidentiality rules approved.
