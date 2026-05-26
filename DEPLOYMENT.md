# Lingualife Site - deployment root

This folder is the exact static payload that should live at the root of the GitHub repo connected to Hostinger.

Expected root structure:
- `index.html`
- `README.md`
- `deploy-meta.json`

When Hostinger deploys this repo into the target directory, the app should open directly without npm or composer build steps.

## Current deployment wiring

- GitHub repository: `artkirakozov/lingualife-site`
- Branch deployed by Hostinger: `main`
- Hostinger domain: `lingualife.evmbot.cloud`
- Hostinger installation path: root directory
- Live app path: `https://lingualife.evmbot.cloud/`
- GitHub webhook: push events trigger Hostinger deployment

## Codex operating workflow

1. Read and edit project files locally in `lingualife-site/`.
2. Validate the static app locally where possible.
3. Commit and push the changed files from `lingualife-site/`.
4. GitHub sends the push webhook to Hostinger.
5. Hostinger pulls `main` into `public_html`.
6. Clear Hostinger cache if the live page does not update immediately.

There is no build step. The deployed payload is the repository content itself.
