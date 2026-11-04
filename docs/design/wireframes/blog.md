# Technical Blog — Wireframe Specification

Task: PORT-T-010
Status: Draft
Page: Technical Blog
Routes: `/blog`, `/blog/[slug]`

## Purpose

Publish engineering articles, technical experiments and
lessons learned to demonstrate expertise in Salesforce,
Agentic AI and Software Engineering.

## Target Users

- Software engineers
- Technical recruiters
- Tech leads
- Engineering managers

## Primary User Goal

Discover relevant technical articles and read them
comfortably on desktop and mobile devices.

## Desktop — Blog Index

Reference viewport: 1440px.

### Header

- Shared navigation.
- Blog item marked as active.

### Introduction

- Page title: Engineering Notes.
- Short description of the blog's technical purpose.

### Featured Article

Optional featured article section containing:

- Article title.
- Short summary.
- Category.
- Estimated reading time.
- Cover image when available.
- Link to the full article.

### Category Filters

- All
- Salesforce
- Agentic AI
- Software Engineering

Expected behavior:

- All published articles appear by default.
- Selecting a category filters visible articles.
- Active filter is distinguishable.
- Empty states are handled.
- Filtering does not require a full-page refresh.

### Article Listing

Desktop:

- Two-column article grid.
- Featured article displayed separately.

Each article card contains:

- Title.
- Short description.
- Category.
- Publication date.
- Estimated reading time.
- Link to the complete article.

Optional:

- Cover image.
- Technology tags.
- Featured flag.

## Mobile — Blog Index

Reference viewport: 390px.

- Single-column article list.
- Featured article stacks vertically.
- Filters wrap or scroll inside their own container.
- Large tap targets.
- No horizontal page overflow.
- Shared accessible mobile navigation.

## Article Detail Layout

Route: `/blog/[slug]`

### Header

- Shared site navigation.
- Breadcrumb or Back to Blog link.

### Article Hero

- Article title.
- Short description.
- Publication date.
- Category.
- Estimated reading time.
- Optional cover image.

### Article Body

- Readable content width.
- Semantic headings.
- Paragraphs and lists.
- Syntax-highlighted code.
- Technical diagrams.
- Tables.
- External references.

### Article Navigation

Desktop:

- Optional table of contents sidebar.

Mobile:

- Compact Jump to Section navigation when useful.

### Article Footer

- Back to Blog link.
- Related articles when available.
- Professional contact or GitHub links.

## Content Management

Blog content will use Astro Content Collections.

Articles will be authored in Markdown or MDX
and versioned in GitHub.

Required metadata:

- Title
- Slug
- Description
- Category
- Publication date
- Draft status

Optional metadata:

- Cover image
- Tags
- Updated date
- Featured flag

Only published articles should appear in the public listing.

## Accessibility Requirements

- Semantic article structure.
- Logical heading hierarchy.
- Keyboard-accessible filters.
- Visible focus indicators.
- Readable text sizing.
- Accessible code examples.
- Appropriate image descriptions.
- Sufficient text contrast.

## Out of Scope

- User comments.
- User authentication.
- Newsletter subscriptions.
- Database-driven article management.
- User-generated content.
- Complex full-text search for MVP.

## Review Checklist

- [ ] Desktop blog index reviewed.
- [ ] Mobile blog index reviewed.
- [ ] Article detail structure reviewed.
- [ ] Category filters approved.
- [ ] Content metadata defined.
- [ ] Accessibility requirements reviewed.
