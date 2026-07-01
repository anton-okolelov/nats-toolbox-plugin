# NATS Toolbox website

Static product site for the NATS Toolbox IntelliJ IDEA plugin.

## Edit content

The landing-page copy, links, feature lists, and screenshot captions live in
[`src/pages/index.md`](src/pages/index.md). The visual shell is implemented in
Astro and renders that Markdown file.

Screenshots live in `src/assets/screenshots/`.

## Develop locally

```bash
pnpm install
pnpm dev
```

Build the production site with:

```bash
pnpm build
```

## Publish

Push `main`, then select **GitHub Actions** as the Pages source in the repository
settings. The workflow in `.github/workflows/deploy.yml` builds and deploys the
site at:

<https://anton-okolelov.github.io/nats-toolbox-plugin/>
