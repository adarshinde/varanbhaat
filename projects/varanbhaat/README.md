# varanbhaat

A modern personal portfolio website with a blog system, built with Astro and deployed on Vercel.

## 🚀 Quick Start

### Development
```bash
npm install
npm run dev
```

Visit `http://localhost:4321` to see your site.

### Production Build
```bash
npm run build
npm run preview
```

### Deploy to Vercel
- Push to GitHub
- Import repository in Vercel
- Site automatically deploys with SSR enabled

## 📝 Adding Blog Posts

Create new posts in `src/content/blog/<topic>/<slug>.md`:

```markdown
---
title: "My Post"
date: 2026-04-06
topic: engineering
description: "Post description"
draft: false
---

# Your content here
```

Topics: `engineering`, `travel`, `life`, `other`

See **PORTFOLIO.md** for detailed documentation.

## 🏗️ Project Structure

```
src/
├── content/blog/          # Markdown blog posts
├── layouts/               # Page templates
├── pages/                 # Routes (home, blog listing, posts)
└── styles/                # Global CSS
```

## ✨ Features

- ✅ Server-side rendering on Vercel
- ✅ Content Collections with type-safe schema
- ✅ Blog grouping by topic and year
- ✅ Tailwind CSS for styling
- ✅ TypeScript support (strict mode)
- ✅ Automatic sitemap and metadata

## 📚 Documentation

See **PORTFOLIO.md** for:
- How to add new posts
- Customization guide
- Troubleshooting
- Tech stack details
