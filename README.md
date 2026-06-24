# aaronlimoges.tech

Personal website and blog built with [Astro](https://astro.build/) using the [Navfolio](https://github.com/dodolalorc/astro-navfolio) template.

---

## Editing content

Content and structure are kept separate. In most cases you only need to touch the files listed below — not anything in `src/pages/`.

### Site-wide settings — `src/config/site.toml`

Everything that appears across the whole site lives here:

- **Profile card** — name, role, location, email, GitHub link
- **Home page** — quote text, intro paragraph, navigation cards, "currently doing" list, connect links
- **Navigation bar** — top-level links
- **Theme** — color palette
- **Search / comments** — enable/disable, provider settings

### Page content — `src/content/`

Written content for individual pages lives here as Markdown (`.md`) or MDX (`.mdx`) files.

| File                             | Page                     |
| -------------------------------- | ------------------------ |
| `src/content/about.mdx`          | About page               |
| `src/content/projects/index.mdx` | Projects page intro      |
| `src/content/blog/*.md`          | Individual blog posts    |
| `src/content/projects/*.md`      | Individual project pages |

Each file starts with a **frontmatter block** between `---` lines for metadata (title, description, date, tags), followed by regular Markdown:

```md
---
title: 'My Post Title'
description: 'A short description.'
date: '2026-06-23'
draft: false
tags:
  - biotech
  - AI
---

Post content goes here in regular Markdown.
```

Set `draft: true` to write something without it appearing on the site.

### Adding a blog post

Create a new `.md` or `.mdx` file in `src/content/blog/`. The filename becomes the URL slug (e.g. `drug-discovery-notes.md` -> `/blog/drug-discovery-notes`).

### Adding a project

Create a new `.md` or `.mdx` file in `src/content/projects/`. Same slug convention as blog posts.

---

## What `src/pages/` does

Pages in `src/pages/` define routing and layout — they pull content from `src/content/` and `site.toml`. You only need to edit these if you want to change the structure or layout of a page, not its text.

---

## Running locally

```bash
bun run dev
```

## Building

```bash
bun run build
```

The site deploys automatically to GitHub Pages via the workflow in `.github/workflows/deploy.yml` on push to `main`.
