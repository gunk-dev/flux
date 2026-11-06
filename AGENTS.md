# Working in this repository

## Product context

Flux is the **umbrella app** for a three-app wellness toolset driven by an AI coach. It implements the **workouts** surface directly. Its siblings are **vibe** (meditation, native Android, separate repo) and **balance** (check-ins and tracking, `gunk-dev/balance`, Capacitor + React, syncs via Google Sheets).

The coach generates programs, reviews progress, adapts to mood, sickness and stress signals from check-ins, and schedules reminders. Flux is one expression of it, so evaluate design and architecture decisions against the coaching relationship, not against Flux as a standalone app.

## Git & GitHub

- **Never mention AI tools or assistants in commits or PRs.** No co-author trailers, attributions, or references in commit messages, PR titles, or PR descriptions.
- **Submit all changes as pull requests.** Never push directly to `main`; work on a feature branch and open a PR.
- **Never merge PRs.** Only the user merges. Do not use `gh pr merge` or any other merge command.

## Environment Management

- **Use nix for all environment management.** This project uses nix flakes. Do not run `npm install` directly.
- **Default dev shell:** `nix develop` (Node.js and serve).
- **Test shell:** `nix develop .#test` (adds Playwright browsers for e2e tests).
- **Run tests:** `nix develop .#test --command npm test`
