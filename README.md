# Flux

A static, mobile-first PWA to track and execute on a fitness goal.

**Live App:** https://flux.gunk.dev

## Features

- Light/dark mode toggle with system preference fallback
- Workout programs loaded from JSON
- Tracks current day (1-365) with localStorage
- Weight logging per exercise with history
- YouTube video embeds for form checks
- Works offline (PWA)

## Stack

- Vanilla HTML/JS/CSS
- No build step required for local development
- Production deploys to fly.io via the gunk-dev preview/prod pipeline; PRs get preview deployments at `https://flux-preview-<PR>.fly.dev/` via the Deploy Flux Preview workflow

## Development

```bash
# Enter dev shell
nix develop

# Start local server
serve .

# Run validation
node tests/validate.js

# Run E2E tests
nix develop .#test
npm ci
npx playwright test
```

## Project Structure

```
├── index.html      # App shell
├── style.css       # Theme styles
├── app.js          # Core logic
├── data/
│   └── program.json   # Workout program data
├── tests/
│   ├── validate.js    # Schema validation
│   └── e2e.spec.js    # Playwright tests
└── PLAN.md         # Project roadmap
```
