# adirondacana

The source for [adirondacana.com](https://adirondacana.com), built with [Astro](https://astro.build) and published through GitHub Pages.

## Write a post

Each post is one Markdown file in `src/content/posts`. The file name becomes the web address, so `first-snow.md` appears at `/blog/first-snow/`.

```md
---
title: "First snow on the ridge"
description: "One or two sentences for the post list and link previews."
date: 2026-10-26
cover: ../../assets/photos/first-snow.jpg
coverAlt: "Describe the cover photo for screen readers."
---

Your writing goes here. Use `## Heading` for section headings.

![Describe this photo](../../assets/photos/another-photo.jpg)
```

- Put photos in `src/assets/photos`. Full-size originals are fine; the site makes smaller versions automatically.
- `cover` and `coverAlt` are optional, but if you add a cover you need the alt text.
- `coverPosition: "50% 30%"` moves the crop focus if a tall photo is cut in the wrong place.
- `draft: true` keeps a post off the live site while you work on it.

Posts written in Word can be converted to this format. Send the .docx and the photo files to Claude and ask for a post file back.

## Other pages

- **About page:** edit `src/pages/about.astro`.
- **Links page:** edit the list in `src/data/links.ts`. The three entries there are examples.
- **Home page photo and tagline:** `src/pages/index.astro`.
- **Colors and fonts:** the first lines of `src/styles/global.css`.

## Preview on your computer

You need [Node.js](https://nodejs.org) 22.23.4 or newer.

```sh
npm install
npm run dev
```

Then open the address it prints (usually http://localhost:4321).

## Publishing

Pushing to the `master` branch rebuilds and publishes the site automatically (see `.github/workflows/deploy.yml`). Updates go live about a minute or two after the push.

One-time setup in the GitHub repository:

1. Open **Settings > Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. Confirm the custom domain still shows `adirondacana.com`. The `CNAME` file in `public` keeps it set.

## Where things live

```
public/             favicon and CNAME (copied to the site as-is)
src/assets/photos/  photos used by pages and posts
src/content/posts/  blog posts (Markdown)
src/data/           the list of outside links
src/pages/          home, blog, about, links, 404, RSS feed
src/layouts/        the shared page frame (head tags, header, footer)
src/styles/         global.css
```

The site also publishes an RSS feed at `/rss.xml` and a sitemap at `/sitemap-index.xml`.
