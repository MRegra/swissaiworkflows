# Swiss AI Workflows — Landing Page

Static one-page landing page for [Swiss AI Workflows](https://mregra.github.io/swissaiworkflows).

Built with plain HTML5 + CSS. No build step, no dependencies, no frameworks.
Open `index.html` in a browser to preview locally.

---

## Project structure

```
ai-biz-onepager/
├── index.html              # One-page landing page
├── assets/
│   ├── css/
│   │   └── styles.css      # All styles — Apple-inspired design system
│   └── images/
│       ├── hero-visual.png         # Hero section visual
│       ├── solution-visual.png     # Solution section visual
│       └── casestudy-visual.png    # Case study section visual
├── CNAME                   # Custom domain (optional)
├── .gitignore
└── README.md
```

> Drop `demo.mp4` (and optionally `demo-poster.jpg`) in the root folder to
> activate the video demo section.

---

## Deploy to GitHub Pages

### Option A — Free subdomain (`mregra.github.io/swissaiworkflows`)

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select **Deploy from a branch**.
4. Select the `main` branch and `/ (root)` folder.
5. Click **Save**.
6. Your site goes live at `https://mregra.github.io/swissaiworkflows` within a minute or two.

### Option B — Custom domain (`yourdomain.com`)

1. Complete Option A first.
2. Create a file named `CNAME` in the repository root containing your domain on a single line:

   ```
   yourdomain.com
   ```

3. In your domain registrar's DNS panel, add:

   | Type  | Name | Value                     |
   |-------|------|---------------------------|
   | A     | @    | 185.199.108.153            |
   | A     | @    | 185.199.109.153            |
   | A     | @    | 185.199.110.153            |
   | A     | @    | 185.199.111.153            |
   | CNAME | www  | `mregra.github.io.`       |

4. In **Settings → Pages**, enter your custom domain and tick **Enforce HTTPS**.
5. DNS changes can take up to 24 hours to propagate.

Reference: [GitHub Pages custom domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

---

## Replace the placeholder links

Search `index.html` for the word `REPLACE` to find every placeholder.

| Placeholder              | Replace with                                                         |
|--------------------------|----------------------------------------------------------------------|
| `#REPLACE-CALENDLY-LINK` | Your Calendly URL, e.g. `https://calendly.com/yourname/15min`       |
| `#REPLACE-FORM-LINK`     | Your Tally or Google Form URL, e.g. `https://tally.so/r/yourform`   |
| `your@email.com`         | Your actual email address                                            |

There are **three** occurrences of `#REPLACE-CALENDLY-LINK` (header, offer section, final CTA) and **two** occurrences of `#REPLACE-FORM-LINK` (hero, how it works).

Quick find in VS Code: `Ctrl+Shift+H` (or `Cmd+Shift+H` on Mac) → search `REPLACE` → replace all at once, or edit each individually.

---

## Update SEO and Open Graph

In the `<head>` of `index.html`, update:

| Tag                          | What to change                          |
|------------------------------|-----------------------------------------|
| `<title>`                    | Your page title                         |
| `<meta name="description">`  | Your meta description (≤ 160 chars)     |
| `<meta property="og:url">`   | Your deployed URL                       |
| `og:image` (commented out)   | Uncomment and add an image (1200×630 px)|
| `<link rel="canonical">`     | Uncomment and set your deployed URL     |

---

## Add a favicon

Place a `favicon.png` file in the repository root, then uncomment this line in `index.html`:

```html
<!-- <link rel="icon" type="image/png" href="favicon.png" /> -->
```

---

## Customise colours and fonts

All design tokens are CSS custom properties at the top of `styles.css` inside the `:root {}` block. Key values:

| Variable             | Default        | What it controls                   |
|----------------------|----------------|---------------------------------|
| `--color-bg`         | `#ffffff`      | Page background                    |
| `--color-bg-alt`     | `#f5f5f7`      | Alternating section background     |
| `--color-bg-dark`    | `#1d1d1f`      | Dark sections (offer, CTA, demo)   |
| `--color-text`       | `#1d1d1f`      | Body text                          |
| `--color-text-muted` | `#6e6e73`      | Secondary / muted text             |
| `--color-accent`     | `#0071e3`      | Buttons, links, highlights         |
| `--font`             | Inter + system | Body and heading font              |

All tokens live in the `:root {}` block at the top of `assets/css/styles.css`.

---

## Customise content

| What to change             | Where to find it in `index.html`                          |
|----------------------------|-----------------------------------------------------------|
| Business name              | `<span class="site-brand">` in header and footer          |
| Price                      | Search for `CHF 300`                                      |
| Pain points list           | `<ul class="pain-list">`                                  |
| Deliverables               | `<ul class="deliverables-list">`                          |
| Good fit / not a fit items | `.offer-card--fit` and `.offer-card--nofit`               |
| Case study text            | `.casestudy-card--before` and `.casestudy-card--after`    |
| FAQ answers                | Each `<details class="faq-item">`                         |
| Footer email               | `<a href="mailto:your@email.com">`                        |
