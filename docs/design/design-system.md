# Developer Portfolio — Design System

Version: 1.0
Task: PORT-T-011
Status: Approved for initial implementation

## Design Principles

The portfolio follows a dark-first visual approach.

The visual language should be:

- Professional and engineering-oriented.
- Minimal and content-focused.
- Accessible and readable.
- Responsive across devices.
- Consistent across projects, articles and navigation.

## Color Palette

| Token            | Value   | Purpose                   |
| ---------------- | ------- | ------------------------- |
| background       | #0B1120 | Main page background      |
| surface          | #111827 | Cards and panels          |
| surface-elevated | #1E293B | Elevated surfaces         |
| foreground       | #F8FAFC | Primary text              |
| muted            | #CBD5E1 | Secondary text            |
| primary          | #38BDF8 | Links and primary actions |
| accent           | #818CF8 | Secondary emphasis        |
| success          | #34D399 | Success indicators        |
| border           | #334155 | Borders and separators    |

## Typography

### Font Families

Body text:
System sans-serif font stack.

Code:
System monospace font stack.

### Typography Hierarchy

- Display: large homepage headline.
- H1: primary page title.
- H2: section heading.
- H3: subsection heading.
- Body: readable paragraph text.
- Small: metadata, timestamps and labels.
- Code: technical examples and snippets.

### Typography Guidelines

- Maintain a consistent heading hierarchy.
- Prefer readable text over decorative typography.
- Use comfortable paragraph line-height.
- Keep long-form content within a readable width.
- Avoid excessively small text.
- Use monospace primarily for code and technical metadata.

## Spacing

The design uses Tailwind CSS spacing utilities.

Custom tokens:

- section: 5rem
- container: 1.5rem

Guidelines:

- Use consistent spacing between sections.
- Maintain generous whitespace around primary content.
- Prefer reusable spacing patterns.
- Avoid arbitrary pixel values when possible.

## Border Radius

- Card: 0.75rem
- Button: 0.5rem

## Components

The following components will follow these tokens:

- Navigation
- Buttons
- Project cards
- Blog cards
- Technology badges
- Section containers
- Technical content blocks
- Footer

Reusable components will be implemented in later tasks.

## Accessibility

- Maintain sufficient contrast for readable text.
- Provide visible keyboard focus indicators.
- Do not communicate meaning using color alone.
- Respect reduced-motion preferences.
- Use semantic headings and HTML landmarks.
- Verify accessibility during implementation.

## Responsive Design

- Mobile-first implementation.
- Single-column layouts on narrow screens.
- Multi-column layouts when space allows.
- No horizontal page overflow.
- Readable content widths.
- Accessible touch targets.

## Implementation

Design tokens are defined in:

`src/styles/global.css`

The implementation uses Tailwind CSS 4 `@theme`.

Examples:

- `bg-background`
- `bg-surface`
- `text-foreground`
- `text-muted`
- `text-primary`
- `border-border`
- `rounded-card`
- `rounded-button`

## Future Improvements

Potential enhancements:

- Light theme.
- Additional semantic color tokens.
- Component variants.
- Motion tokens.
- Typography refinements.

These enhancements are outside the initial scope
of PORT-T-011.
