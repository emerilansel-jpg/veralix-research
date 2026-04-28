# Veralix Research

Veralix Research is a production-ready Astro static website for an independent market intelligence firm. The project includes a polished editorial homepage, an about page, dynamic research article pages, structured schema markup, and a Decap CMS admin area for managing long-form research content.

## Tech Stack

- Astro with static output
- Decap CMS
- Cloudflare Pages
- GitHub

## Local Development

1. Install dependencies:

   ```bash
   npm install
   ```

2. Start the local development server:

   ```bash
   npm run dev
   ```

3. Open the local URL shown in the terminal to view the site.

## Build for Production

Run the production build locally before deploying:

```bash
npm run build
```

Astro will generate the static site into the `dist/` directory.

## Cloudflare Pages Deployment

1. Push this repository to GitHub.
2. In Cloudflare Dashboard, go to `Workers & Pages`.
3. Click `Create` and choose `Pages`.
4. Select `Connect to Git`.
5. Authorize GitHub if prompted and choose the `veralix-research` repository.
6. Use the following build settings:
   - Framework preset: `Astro`
   - Build command: `npm run build`
   - Build output directory: `dist`
   - Environment variable: `NODE_VERSION=20`
7. Save and deploy.

## Spaceship Domain Connection

1. Open the deployed Pages project in Cloudflare.
2. Go to `Custom Domains`.
3. Add `veralixresearch.com`.
4. Cloudflare will display two required nameservers.
5. In Spaceship, open the domain management page for `veralixresearch.com`.
6. Switch the domain to custom nameservers.
7. Enter the two Cloudflare nameservers exactly as provided and save the update.
8. Allow time for DNS propagation.

## Decap CMS

The CMS admin interface is available at:

```text
/admin
```

Before using the CMS in production:

1. Replace `GITHUB_USERNAME` in `public/admin/config.yml` with the real GitHub username that owns the repository.
2. Ensure the GitHub repository is public or that Decap authentication is configured for private access.
3. Commit and redeploy the site so the CMS backend points to the correct repository.

## Content Management

Research articles live in:

```text
src/content/research
```

Each article uses Markdown frontmatter for title, date, author, category, tags, description, and featured image.
