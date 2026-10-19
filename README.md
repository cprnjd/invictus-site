# Invictus Life Care Planning — Website

A complete replacement for invictuslifecare.com. No build step, no
dependencies — plain HTML and CSS that can be uploaded to any web host.

Design: matches the Invictus Mediation site (same layout, typography, and page
structure), recolored to a **light blue on seafoam** palette — deep blue to
turquoise gradients (#0e2f56 → #107a94), light blue (#8fe3f2) and turquoise
(#2cc5dd) accents, seafoam (#e1f3f5) page background, black text. No green.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Home — hero, about/credentials, contact cards |
| `blog/index.html` | Blog index — posts, newest first |
| `blog/<slug>/index.html` | One folder per blog post |
| `css/styles.css` | Shared stylesheet (all colors defined at the top in `:root`) |
| `sitemap.xml` | Homepage, blog index, and posts |

There is intentionally **no calendar/scheduling page** — engagement starts by
phone, text, or email.

## Key facts baked into the site

- **Rates are not published on the site.** Engagement terms are sent to the client
  directly; nothing on the site quotes a rate or retainer.
- **Phone:** (561) 305-8877 · **Email:** chris@chrispittaluga.com
- **Mail:** PO Box 6143, Delray Beach, FL 33482 · **Hours:** Mon–Fri 9am–4pm ET

## Adding a blog post

Posts are plain HTML. There is no build step. Copy an existing post and edit it.

1. Copy a folder under `blog/` and rename it to the new URL slug, so the page is `blog/<slug>/index.html` (public URL `/blog/<slug>/`).
2. In the new `index.html`, set `<title>` to the SEO title. Update the meta description, canonical URL, Open Graph tags, and the Article JSON-LD (`headline`, `description`, `datePublished`, `dateModified`, and the page URL). Author stays Chris Pittaluga, RN, JD, CLCP. Publisher stays Invictus Life Care Planning.
3. Set the visible `<h1>` to the post title, and set the date and category. Paste the article body only. Do not include the settings comment block (post title, SEO title, slug, description, category, tags, image idea).
4. End the post with a neutral summary. Do not add a call to action, a phone number, or an email address, and do not close by addressing plaintiff or defense attorneys. Keep the Sources line and the Disclaimer when the post has them.
5. Add a card at the **top** of `blog/index.html` with the title, date, and a short excerpt.
6. Add the post URL to `sitemap.xml`, and set the blog index `<lastmod>` to the new post's date.

A future publish date is fine. The page is included as soon as it is in the repo. Do not add an image unless a real image file is already in the project.

Preview with a local server (directory URLs need one):

```
npx --yes serve -l 4173 .
```

## Adding your photo

In `index.html`, find the comment `To add a photo` (in the About section).
Save your photo as `images/christiane.jpg` and remove the `<!--` / `-->`
comment markers around the portrait block. The photo will appear above the
"Why Invictus?" panel.

## Publishing (replacing the current site)

The current site is hosted at **invictuslifecare.com**. Options:

1. **Same host:** If the domain is on Squarespace/Wix, those platforms can't
   host raw HTML files — you'd point the domain at new hosting instead.
2. **Netlify (free, easiest):** Go to [app.netlify.com/drop](https://app.netlify.com/drop)
   and drag this whole folder onto the page. Then connect the
   `invictuslifecare.com` domain in Netlify's domain settings and update DNS
   at your registrar.
3. **Any web host:** Upload the folder contents (index.html, css/, and the
   redirect stubs) to the web root via the host's file manager or FTP.

## Editing

- **Colors:** all in `:root` at the top of `css/styles.css`
- **Phone/email/address:** search for `305-8877`, `chrispittaluga.com`, `PO Box`

## Local preview

Open `index.html` directly in a browser, or run a local server:

```
npx --yes serve -l 4173 .
```
