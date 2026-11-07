# jasonrutterford-cyber.github.io

Jason Rutterford's site. Hosted free on GitHub Pages, built by Jekyll (GitHub runs it for you; nothing to install).

## Go live (no Terminal needed, about 15 minutes)

1. **Create a GitHub account** at github.com. The account is **jasonrutterford-cyber** — the site's address is built from it: `https://jasonrutterford-cyber.github.io`. (If that username is taken, use another; the address becomes `https://<username>.github.io`. Update `url:` in `_config.yml` to match.)
2. **Create the repository.** Click the **+** (top right) → **New repository**. Name it exactly `jasonrutterford-cyber.github.io` (your username + `.github.io`). Public. Don't tick any of the "initialise" boxes. Click **Create repository**.
3. **Upload the site.** On the empty repository page click **uploading an existing file**. Open this folder in Finder, select everything inside it (including the folders that start with `_`), and drag them all onto the GitHub page. Wait for the upload bar, then click **Commit changes**.
   - Finder hides files that start with a dot. The only one that matters is `.gitignore` and it's optional, so don't worry about it.
4. **Wait two minutes**, then open `https://jasonrutterford-cyber.github.io`. If it shows a 404, wait another minute and refresh. First builds can take up to ten.
5. **Check it builds.** Click the **Actions** tab in the repository. A green tick means it built. A red cross means a typo in a file — click it and the message says which line.

That's it. The site is now live, free, and yours.

## Posting a new article

Articles live in the `_posts` folder, one Markdown file each, named `YYYY-MM-DD-short-title.md`. Copy the existing one as a template. The top of the file looks like this:

```
---
title: "The headline"
subtitle: "One sentence under the headline (optional)"
date: 2026-11-14
cover: /assets/img/posts/your-image.png
cover_alt: "A plain description of the image for screen readers"
tags: [Service design, AI]
---

First paragraph. This shows as the summary on the Writing page.

<!--more-->

The rest of the article in Markdown. ## for headings, **bold**, - for bullets, > for a quote.
```

To publish: in GitHub, open `_posts` → **Add file** → **Upload files** (or **Create new file** and paste), then **Commit changes**. Images go in `assets/img/posts/`. The site rebuilds itself in a minute or two.

Simplest workflow: ask Claude to write the post file and the cover image, then upload the two files.

## Changing contact details, newsletter, wording

Everything you'd normally change is at the top of `_config.yml`:

- `contact:` — email, LinkedIn and X links. Set one to `""` to hide it.
- `newsletter:` — see below.
- `description:` / `tagline:` — what search engines and link previews show.

Page text lives in `index.html`, `about.md` and `contact.html`. Edit them in GitHub (pencil icon) and commit.

## Turning on the newsletter

The newsletter box is switched off (`enabled: false` in `_config.yml`). Set it to `true` to show it; until you set a provider it shows an "Email me 'subscribe'" button. When you're ready for a real form:

**Kit (kit.com, free to 10,000 subscribers)**
1. Create a Kit account and a form (Grow → Landing Pages & Forms → Create → Form → Inline).
2. Click **Publish** → **HTML**. Find `action="https://app.kit.com/forms/XXXXX/subscriptions"` in the code.
3. In `_config.yml` set `action:` to that URL and `field_name: "email_address"`.

**Buttondown (buttondown.com, free to 100 subscribers)**
1. Create an account with username `jasonrutterford`.
2. In `_config.yml` set `action: "https://buttondown.com/api/emails/embed-subscribe/jasonrutterford"` and `field_name: "email"`.

Commit the change and the real sign-up form appears everywhere.

## Your own domain later

If you ever buy `jasonrutterford.com`: add a file called `CNAME` containing just `jasonrutterford.com`, point the domain's DNS at GitHub Pages (Settings → Pages shows the records), and change `url:` in `_config.yml`. Nothing else changes and the old address redirects.

## Swapping in the generated illustrations

The site expects six images in `assets/img/illustrations/`, by these exact names:
`hero.png` (landscape), `contact.png` (landscape), `about-banner.png` (wide landscape), `discovery.png`, `strategy.png`, `leadership.png` (square).
Replace any of them with a new file of the same name and the page picks it up on the next build. Keep the flat light-grey background (#F2F2F3); the site frames each image in a panel.

## Files

```
_config.yml        settings (contact, newsletter, title)
index.html         home page
writing.html       list of articles
about.md           about page
contact.html       contact page
_posts/            one file per article
_layouts/          page templates
_includes/         illustrations (SVG), newsletter box, icons
assets/css/        the stylesheet (brand colours at the top)
assets/img/        images; posts/ for article covers
```

Brand: Instrument Sans (headings condensed), ink `#151A22` on paper `#F2F2F3`, gradient green `#14B87A` → blue `#2F6BFF` → purple `#7B3FE4`, white cards with ink outlines and a grey offset shadow, outlined stick-figure illustrations with tilted gradient tiles.
