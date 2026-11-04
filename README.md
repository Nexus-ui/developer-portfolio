## Development Environment

This portfolio is built with Astro, TypeScript and Tailwind CSS,
and deployed to Cloudflare Workers.

### Prerequisites

- Node.js (supported LTS version recommended)
- npm
- Git
- Visual Studio Code (recommended)

### Local Setup

Clone the repository:

```bash
git clone https://github.com/Nexus-ui/developer-portfolio.git
cd developer-portfolio
```

Install dependencies:

```bash
npm ci
```

Start the local development server:

```bash
npm run dev
```

Open http://localhost:4321 in your browser.

### Production Build

Generate the static website:

```bash
npm run build
```

The generated files are stored in `dist/`.

The `dist/` and `node_modules/` directories are not committed
to Git.

## Git Workflow

The `main` branch represents the production codebase.

Development follows a feature-branch workflow:

1. Update the local `main` branch.
2. Create a branch for the assigned task.
3. Implement and test changes locally.
4. Commit changes with the task ID.
5. Push the branch to GitHub.
6. Open a Pull Request targeting `main`.
7. Review the changes and verify the Cloudflare Preview.
8. Merge the Pull Request after all checks pass.
9. Update the local `main` branch.

Example branch:

`feat/PORT-T-011-design-tokens`

Example commit:

`feat: add design tokens [PORT-T-011]`

## Deployment

Production is hosted on Cloudflare Workers.

Production URL:

https://developer-portfolio.pietro-messina.workers.dev

### Automated Deployment

Cloudflare Workers Builds is connected to the GitHub repository.

Production branch: `main`

Build command:

```bash
npm run build
```

Deploy command:

```bash
npx wrangler deploy
```

Every push to `main` triggers a production build and deployment.

### Preview Deployments

Pull Requests can trigger isolated Cloudflare Preview deployments.

The preview command is:

```bash
npx wrangler preview
```

The Wrangler configuration includes:

```json
"previews": {}
```

Preview deployments allow changes to be tested before merging
them into the production branch.

## Rollback Procedure

If a production deployment introduces a problem:

1. Open the Cloudflare Dashboard.
2. Navigate to Workers & Pages.
3. Select `developer-portfolio`.
4. Open the Deployments tab.
5. Identify the last known working deployment.
6. Open the three-dot menu for that version.
7. Select Rollback and confirm.
8. Verify that the production website works correctly.

A rollback restores the deployed Worker version, but does not
revert GitHub commits.

After an emergency rollback, create a corrective branch and
Pull Request so the `main` branch matches the intended
production state before the next deployment.

## Environment Configuration

The MVP is a static Astro website without a database or
server-side application.

No application API keys are currently required.

Security guidelines:

- Never commit passwords, tokens or API keys.
- Keep local environment files out of Git.
- Do not publish private customer or company information.
- Use Cloudflare-managed secrets for future server-side features.
- Do not expose sensitive values through client-side variables.

## Troubleshooting

If the website does not build locally:

```bash
npm ci
npm run build
```

If Cloudflare Preview fails:

- Open the failed build logs.
- Verify `wrangler.jsonc`.
- Check that the `previews` configuration is present.
- Confirm that the Astro build succeeds.
- Push the fix to the existing feature branch.

If production is unavailable after deployment, follow the
rollback procedure above.
