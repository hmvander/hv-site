# Heidi Vandermeer — Personal Website

Astro-based personal website for B2B marketing, AI, growth systems, ideas, and experiments.

## Tech
- Astro
- Semantic HTML
- Modern CSS
- Minimal JavaScript
- Static output suitable for Cloudflare Pages

## Local setup
```bash
npm install
npm run dev
```
Astro will print the local URL, typically `http://localhost:4321`.

## Production build
```bash
npm run build
npm run preview
```
The generated static site is written to `dist/`.

## GitHub setup
```bash
git init
git add .
git commit -m "Initial personal site"
git branch -M main
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
```

## Cloudflare Pages

The repository root must contain `package.json`, `src/`, and `public/` directly. Do not put the project inside an extra `heidi-site/` folder in GitHub.

For a Cloudflare **Pages** Git deployment:
1. In **Workers & Pages**, create/select a **Pages** project and connect this GitHub repository.
2. Framework preset: **Astro**.
3. Root directory: `/` (repository root).
4. Build command: `npm run build`.
5. Build output directory: `dist`.
6. Leave the deploy command blank; Pages deploys the `dist` directory after a successful build.

A successful Astro build should report three generated routes (`/`, `/ideas/`, and `/about/`), not `0 page(s) built`.

If Cloudflare is instead configured as a Workers Builds project and requires a deploy command, use a Pages project for this static version rather than `npx wrangler deploy`.

## Update before publishing
Search the codebase for these placeholders:
- `https://example.com` → your production domain
- `hello@example.com` → your email address

The LinkedIn URL is currently set to:
- `https://www.linkedin.com/in/heidivandermeer`

## Where to edit content
- Homepage: `src/components/`
- Hero: `src/components/Hero.astro`
- Focus areas: `src/components/FocusAreas.astro`
- Selected ideas: `src/components/SelectedIdeas.astro`
- About preview: `src/components/AboutPreview.astro`
- Connect section: `src/components/Connect.astro`
- Global visual system: `src/styles/global.css`

## Portrait
A portrait can later be added at:
`public/images/heidi-vandermeer.jpg`

The current homepage intentionally uses a polished abstract placeholder so the site works without photography.

## Social preview
Add an Open Graph/social image at:
`public/images/og-default.jpg`

## Future ideas architecture
The Selected Ideas component is currently data-driven inside the component. It can later be moved into Astro content collections or Markdown without redesigning the card system.
