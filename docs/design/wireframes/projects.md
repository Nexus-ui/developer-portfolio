# Projects Explorer — Wireframe Specification

Task: PORT-T-010
Status: Draft
Page: Projects Explorer
Route: `/projects`

## Purpose

Allow recruiters, engineering managers and technical reviewers
to discover engineering projects relevant to their interests.

## Primary User Goal

Find projects by specialization and navigate to a technical
case study with minimal interaction.

## Desktop Layout

Reference viewport: 1440px.

### Header

- Shared navigation with the Homepage.
- Projects navigation item has an active state.

### Introduction

- Page heading: Selected Engineering Projects.
- Brief explanation of the portfolio's technical focus.

### Project Filters

Categories:

- All
- Salesforce
- Agentic AI
- Software Engineering

Expected behavior:

- All projects are displayed by default.
- Selecting a category filters visible projects.
- The selected category is visually distinguishable.
- The number of visible projects updates.
- An empty state appears if no projects match.
- Filtering should not require a full-page reload.

### Project Grid

Desktop layout:

- Three-column grid on wide screens.
- Two-column grid on medium screens.
- One-column layout on narrow screens.

Each project card contains:

- Project thumbnail or architecture illustration.
- Project title.
- Short description.
- Specialization.
- Main technologies.
- Link to the technical case study.

Optional metadata:

- GitHub repository.
- Live demo.
- Project status.

## Mobile Layout

Reference viewport: 390px.

- Shared mobile navigation.
- Single-column project cards.
- Filters wrap or scroll horizontally without page overflow.
- Card details remain readable.
- Cards offer sufficiently large tap targets.
- Project links remain clearly visible.

## Navigation

- Project card -> `/projects/[slug]`
- GitHub links open external repositories.
- Live demo links open external applications.
- Main navigation remains consistent with other pages.

## Content Model

Each project requires:

- Title
- Slug
- Category
- Short description
- Technologies
- Publication status

Optional:

- Thumbnail
- GitHub URL
- Demo URL
- Featured flag
- Results summary

## Accessibility Requirements

- Filters must be keyboard accessible.
- Active filters must be identifiable beyond color alone.
- Project cards must use semantic links.
- Images must have appropriate alternative text.
- Focus indicators must remain visible.
- Filter updates must preserve usability for assistive technology.

## Out of Scope

- User accounts.
- Saved projects.
- User ratings.
- Database-backed search.
- Complex sorting.
- Server-side filtering.

## Review Checklist

- [ ] Desktop project grid reviewed.
- [ ] Mobile project grid reviewed.
- [ ] Category filter interaction approved.
- [ ] Project card information hierarchy approved.
- [ ] Empty state behavior documented.
- [ ] Navigation and accessibility reviewed.
