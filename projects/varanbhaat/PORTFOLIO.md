# varanbhaat — Personal Portfolio Website

A modern, SSR-ready personal portfolio website built with Astro, deployed on Vercel.

## Quick Start

### Development
```bash
npm install
npm run dev
```

Visit `http://localhost:4321` to see the site in development mode.

### Build & Deploy
```bash
npm run build
npm run preview
```

To deploy to Vercel, push to GitHub and import the repository into Vercel — the Astro adapter handles all configuration automatically.

---

## Project Structure

```
varanbhaat/
├── src/
│   ├── content.config.ts      # Content Collection schema (defines blog frontmatter)
│   ├── content/
│   │   └── blog/
│   │       ├── engineering/   # Engineering blog posts
│   │       ├── travel/        # Travel blog posts
│   │       └── ...
│   ├── layouts/
│   │   ├── BaseLayout.astro   # HTML shell with nav and footer
│   │   └── BlogLayout.astro   # Post layout wrapper
│   ├── pages/
│   │   ├── index.astro        # Home page with recent posts
│   │   └── blog/
│   │       ├── index.astro    # Blog listing page (grouped by topic)
│   │       └── [...slug].astro # Dynamic SSR post pages
│   └── styles/
│       └── global.css          # Global Tailwind + custom styles
├── astro.config.mjs            # Astro config (SSR + Vercel adapter)
├── tailwind.config.mjs         # Tailwind CSS config
├── tsconfig.json               # TypeScript config
└── package.json                # Dependencies
```

---

## Adding New Blog Posts

Blog posts are simple Markdown files stored in `src/content/blog/`. The folder structure determines the topic grouping.

### How to Add a Post

1. Create a new `.md` file in `src/content/blog/<topic>/<slug>.md`
   - `<topic>` can be: `engineering`, `travel`, `life`, or `other`
   - `<slug>` is the URL-friendly name (e.g., `first-trip.md`)

2. Add frontmatter to the file:
```markdown
---
title: "Post Title Here"
date: 2026-04-06
topic: engineering
description: "A brief description of the post"
draft: false
---

# Your content here

Write your post in standard Markdown syntax.
```

3. The post is automatically:
   - Validated against the schema in `src/content.config.ts`
   - Rendered with the `BlogLayout.astro` wrapper
   - Listed on the `/blog` page, grouped by topic
   - Accessible at `/blog/<topic>/<slug>`

### Example Post Structure

```
src/content/blog/
├── engineering/
│   ├── hello-world.md
│   ├── astro-tips.md
│   └── css-tricks.md
└── travel/
    ├── first-trip.md
    └── japan-adventure.md
```

This creates URLs like:
- `/blog/engineering/hello-world`
- `/blog/travel/first-trip`

---

## Blog Collection Schema

Posts must include the following frontmatter fields:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `title` | string | Yes | Post title |
| `date` | date | Yes | Publication date (YYYY-MM-DD format) |
| `topic` | enum | Yes | One of: `engineering`, `travel`, `life`, `other` |
| `description` | string | No | Short excerpt (shown in listings) |
| `draft` | boolean | No | Set to `true` to hide from listings (default: `false`) |

---

## Styling

The site uses **Tailwind CSS** for styling. Global styles are in `src/styles/global.css`.

### Customization

- Edit `tailwind.config.mjs` to customize colors, fonts, and spacing
- Modify `BaseLayout.astro` to change the overall structure (nav, footer, etc.)
- Update `BlogLayout.astro` to customize how individual posts are styled
- Edit component styles directly in `.astro` files or in `global.css`

---

## Deployment to Vercel

The project is configured for **Server-Side Rendering (SSR)** on Vercel using the `@astrojs/vercel` adapter.

### Steps to Deploy

1. Push your code to GitHub
2. Go to [Vercel](https://vercel.com) and click "New Project"
3. Import your GitHub repository
4. Vercel auto-detects Astro and uses the adapter configuration
5. Your site is live! 🚀

### Environment Variables

If you need environment variables, add them in the Vercel dashboard under "Settings" → "Environment Variables". They'll be available in your Astro code via `import.meta.env`.

---

## Tech Stack

- **Framework**: Astro 6.x (static site generation + SSR)
- **Styling**: Tailwind CSS 3.4+
- **Hosting**: Vercel (SSR via `@astrojs/vercel/serverless`)
- **Content**: Markdown with Astro Content Collections
- **Language**: TypeScript (strict mode)

---

## Next Steps

- [ ] Customize the home page hero section with your name and bio
- [ ] Add your own blog posts to `src/content/blog/`
- [ ] Update the footer with your contact information
- [ ] Add social media links to the navigation
- [ ] Deploy to Vercel and set up a custom domain
- [ ] Add more complex styling and animations to the home page

---

## Useful Commands

```bash
npm run dev       # Start dev server
npm run build     # Build for production
npm run preview   # Preview production build locally
npm run astro     # Run Astro CLI directly
```

---

## Troubleshooting

### Site not loading?
- Ensure all `.md` files have proper frontmatter
- Check that `date` is in `YYYY-MM-DD` format
- Verify `topic` is one of the four allowed values

### Build fails?
- Run `npm install --legacy-peer-deps` to reinstall dependencies
- Check TypeScript errors: the project uses `strict` mode
- Review the build output for specific error messages

### Changes not showing?
- Hard refresh your browser (Ctrl+Shift+R or Cmd+Shift+R)
- For Vercel deployments, wait a few seconds for the build to complete

---

## License

This project is open source. Feel free to customize and use it for your own portfolio!

Happy blogging! ✍️