# Homepage Wireframe Specification

Task: PORT-T-010
Status: Draft
Page: Home
Route: `/`

## Purpose

Introduce the developer's professional identity and guide
visitors toward technical projects, resume and contact details.

## Target Users

- Technical recruiters
- Engineering managers
- Tech leads and software architects

## Primary User Goal

Understand the developer's specialization and navigate to
relevant projects within two clicks.

## Desktop Layout

Reference viewport: 1440px.

### 1. Header

- Portfolio logo or developer initials.
- Navigation: Projects, Blog, About, Resume, Contact.
- Sticky navigation can be considered during implementation.

### 2. Hero Section

- Professional title: Software Engineer.
- Headline emphasizing problem solving and engineering.
- Specializations: Salesforce, Agentic AI, Software Engineering.
- Primary CTA: Explore Projects.
- Secondary CTA: Download Resume.
- Optional technical illustration or original visual.

### 3. Specializations

Three cards:

1. Salesforce Development
2. Agentic AI Engineering
3. Software Engineering

Each card includes a short description and links to
relevant projects.

### 4. Featured Projects

- Display up to three featured projects.
- One representative project per specialization.
- Each card shows project name, summary and technologies.
- Each card links to the full technical case study.
- Include a View All Projects link.

### 5. Contact CTA

- Short invitation to connect professionally.
- Contact action using email or LinkedIn.

### 6. Footer

- GitHub profile.
- LinkedIn profile.
- Copyright information.
- Secondary navigation when useful.

## Mobile Layout

Reference viewport: 390px.

- Navigation collapses into an accessible mobile menu.
- Hero content uses a single-column layout.
- Primary CTA appears before secondary actions.
- Hero visual moves below the introductory content.
- Specializations appear in a vertical stack.
- Featured projects use single-column cards.
- Contact CTA remains clearly visible.
- No horizontal scrolling.

## Functional Requirements

- All navigation links must work.
- Project cards navigate to corresponding case studies.
- Resume link downloads or opens the CV.
- Contact CTA opens the selected contact channel.
- Page is responsive across supported viewport widths.
- Keyboard navigation and visible focus are supported.

## Accessibility Considerations

- Use semantic HTML landmarks.
- Maintain a logical heading hierarchy.
- Provide accessible labels for navigation controls.
- Ensure sufficient text contrast.
- Provide appropriate alt text for meaningful images.
- Respect reduced-motion preferences.

## Content Requirements

- Professional headline in English.
- Brief and verifiable professional introduction.
- Three specialization descriptions.
- Featured project metadata.
- Public professional links.

## Out of Scope

- Authentication.
- Contact form backend.
- Dynamic personalization.
- AI chatbot on the homepage.
- Animated 3D experiences.

## Review Checklist

- [ ] Desktop layout reviewed.
- [ ] Mobile layout reviewed.
- [ ] Content hierarchy approved.
- [ ] Primary navigation approved.
- [ ] CTA placement approved.
- [ ] Accessibility requirements reviewed.
