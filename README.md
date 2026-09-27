# Considered Chaos — A Study Guide to Eugene Healey

A single-page, self-contained study guide to the published work of the brand strategist
**Eugene Healey**: the post-social era, brand as mosaic, post-luxury status symbols, the
death of the middle, and the critical theory underneath them.

Sixty-three takes drawn from 24 essays and 41 short films, plus an interactive system map,
a mosaic builder and an attention sorter. No build step, no dependencies, no tracking.

---

## Deploy to GitHub Pages

**1. Create the repo and push these files to the root of the default branch.**

```bash
cd considered-chaos-site
git init -b main
git add .
git commit -m "Considered Chaos study guide"
git remote add origin git@github.com:USERNAME/considered-chaos.git
git push -u origin main
```

**2. Turn on Pages.** Repo → *Settings* → *Pages* → **Source: Deploy from a branch**,
branch `main`, folder `/ (root)`. Save. The first build takes a minute or two.

**3. Your site is at** `https://USERNAME.github.io/considered-chaos/`

### Two flavours of Pages URL

| You want | Name the repo | URL |
|---|---|---|
| A project site | anything, e.g. `considered-chaos` | `https://USERNAME.github.io/considered-chaos/` |
| Your root user site | `USERNAME.github.io` | `https://USERNAME.github.io/` |

---

## If the URL in the metadata is wrong

Three files carry the absolute site URL, because social-card scrapers and sitemaps need one:
`index.html`, `robots.txt` and `sitemap.xml`.

If this package was built with the `USERNAME` placeholder, or you move the site, run a
find-and-replace over those three files:

```bash
OLD="https://USERNAME.github.io/considered-chaos"
NEW="https://your-real-url.example"          # no trailing slash
for f in index.html robots.txt sitemap.xml; do
  perl -pi -e "s{\Q$OLD\E}{$NEW}g" "$f"
done
```

Everything else — icons, manifest, the 404 page — uses relative paths and will work
wherever the site is served from, including a plain `file://` open or a custom domain.

---

## What is in here

| File | Purpose |
|---|---|
| `index.html` | The guide. Everything is inline: ~260 KB, one HTTP request plus Google Fonts. |
| `404.html` | On-brand not-found page. GitHub Pages serves this automatically. |
| `favicon.svg` | Primary icon for modern browsers. |
| `favicon.ico` | Multi-size fallback (16→256 px). The 16 and 24 px entries use a simplified four-tile mark so the tab icon stays legible. |
| `favicon-16.png`, `favicon-32.png` | Explicit PNG sizes for older browsers. |
| `apple-touch-icon.png` | 180×180, full bleed, no transparency — iOS applies its own mask. |
| `icon-192.png`, `icon-512.png` | Web app manifest icons, including a maskable entry. |
| `og-image.png` | 1200×630 social card for Open Graph and Twitter. |
| `site.webmanifest` | Installable web app metadata. |
| `robots.txt`, `sitemap.xml` | Crawling and indexing. |
| `.nojekyll` | Tells Pages to serve files as-is and skip the Jekyll build. |

---

## A note on custom domains

Add a `CNAME` file containing just your domain (e.g. `chaos.example.com`), point a DNS
`CNAME` record at `USERNAME.github.io`, then set the domain under *Settings → Pages*.
Remember to re-run the URL find-and-replace above.

---

## Provenance and licence

The guide is an **unofficial educational reference**, compiled September 2026 from
publicly available work: the [Considered Chaos newsletter](https://eugenehealey.substack.com/),
short films at [@eugbrandstrat](https://www.tiktok.com/@eugbrandstrat), and his writing in
*The Guardian*. It is **not affiliated with or endorsed by Eugene Healey**.

Quotations are his — those from essays as written, those from short films taken from the
platform's automatic captions and lightly punctuated. The framing, the groupings, the
numbers in the interactive tools and the models themselves are an interpretation of his
arguments, not his material.

If you find this useful, go and read and watch the originals. Every one of them is linked
from the **Source library** tab inside the guide.

If Eugene would prefer this not be published, take it down.
