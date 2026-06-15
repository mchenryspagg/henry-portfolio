# Henry Okam — Salesforce Portfolio Site

Static personal portfolio showcasing Salesforce CRM and data-analytics work. Single index page + per-project case study pages. Designed to be hosted on GitHub Pages and embedded into other sites via iframe.

## Tech

- Plain HTML + Tailwind CSS (via CDN — zero build)
- Inter font via Google Fonts
- Vanilla JS only for the year stamp and the `?embed=1` toggle

## Files

```
henry-portfolio/
  index.html        ← hero, about, featured project (Velociti), other projects, skills, contact
  velociti.html     ← full Velociti Bikes case study
  delta.html        ← Delta Airlines summary (full case study placeholder)
  README.md
  .nojekyll
  .gitignore
```

## Local preview

Just open `index.html` in any browser.

## Deploy to GitHub Pages

1. Create a new repo (e.g. `henry-portfolio`)
2. From this folder:
   ```
   git init
   git add .
   git commit -m "Initial portfolio site"
   git branch -M main
   git remote add origin https://github.com/<your-user>/henry-portfolio.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Branch `main` / `(root)` → Save**
4. Live at `https://<your-user>.github.io/henry-portfolio/` in about a minute.

## Embedding into another site

GitHub Pages does **not** send the `X-Frame-Options` header, so the site can be safely iframed. Use `?embed=1` to hide the nav and footer for a cleaner embed.

### Embed the whole portfolio

```html
<iframe
  src="https://<your-user>.github.io/henry-portfolio/?embed=1"
  width="100%"
  height="900"
  frameborder="0"
  loading="lazy"
  title="Henry Okam — Salesforce Portfolio">
</iframe>
```

### Embed just the Velociti case study

```html
<iframe
  src="https://<your-user>.github.io/henry-portfolio/velociti.html?embed=1"
  width="100%"
  height="1200"
  frameborder="0"
  loading="lazy"
  title="Velociti Bikes — Salesforce CRM Case Study">
</iframe>
```

### Embed the Delta Airlines summary

```html
<iframe
  src="https://<your-user>.github.io/henry-portfolio/delta.html?embed=1"
  width="100%"
  height="800"
  frameborder="0"
  loading="lazy"
  title="Delta Airlines — Salesforce + Data Project">
</iframe>
```

> **Sizing tip:** `height` is a guess. Tune it to your container. Long pages will scroll within the iframe.

## Go-live checklist

**Contact & identity:**
- [ ] Replace placeholder LinkedIn URL on `index.html` (currently `#`)
- [ ] Replace placeholder Trailblazer URL on `index.html` (currently `#`)
- [ ] Confirm email `okam.h@northeastern.edu` is the address you want public
- [ ] Confirm phone `+234 806 370 6531` should be public on the site
- [ ] Update the Velociti live-demo URL on `index.html` and `velociti.html` if the deployed site lives somewhere other than `https://mchenryspagg.github.io/velociti-bike/`

**Project source links (currently `href="#"` placeholders):**

*Velociti case study*
- [ ] Replace `View presentation` link on `velociti.html` with the slide-deck URL (Gamma / Google Slides / PDF)

*Delta case study*
- [ ] Replace `View full report` link on `delta.html` with the analytics-report URL (Google Doc / PDF)
- [ ] Replace `View Colab notebook` link on `delta.html` with the Colab URL
- [ ] Replace `View discovery presentation` link with the Gamma URL for *Addressing Delta Airlines' AI, Data, and Marketing Integration Challenges*
- [ ] Replace `View integration proposal` link with the Gamma URL for *Delta Airlines Data & AI Integration Proposal*

**Optional:**
- [ ] Add a profile photo to `assets/` and reference it in the hero
- [ ] Custom domain (e.g. `henryokam.dev`) — add a `CNAME` file with the domain, then point a DNS `CNAME` record at `<your-user>.github.io`

## Per-project palette overrides

Each case-study page has its own colour accent palette layered on top of the site-wide Salesforce-inspired master palette:

- **`velociti.html`** — Velociti's own brand: teal `#0A6E68`, navy `#1B4F72`, red `#A61C00`. Applied in the page-level Tailwind config as `velociti.teal/navy/red`.
- **`delta.html`** — aviation palette: navy `#003366`, sky `#5B9BD5`, red `#C8102E`, mist `#EAF2F8`. Applied as `delta.navy/sky/red/mist`.
- **`index.html`** — registers both project palettes so the featured Velociti card and the Delta card can render in their own accent colours while the surrounding site frame (nav, about, skills, contact, footer) stays on the master Salesforce blue palette.

When adding a new project, follow the same pattern: pick a 3–4 colour scale, extend the Tailwind config on both `index.html` and the new case-study page, and apply only to that project's regions.

## Adding a new project later

1. Copy `delta.html`, rename to `[project-slug].html`
2. Edit content
3. Add a new card in the "Other projects" grid on `index.html`
4. Commit + push — GitHub Pages updates automatically
