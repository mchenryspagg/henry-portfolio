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

- [ ] Replace placeholder LinkedIn URL on `index.html` (currently `#`)
- [ ] Replace placeholder Trailblazer URL on `index.html` (currently `#`)
- [ ] Confirm email `okam.h@northeastern.edu` is the address you want public
- [ ] Confirm phone `+234 806 370 6531` should be public on the site
- [ ] Update the Velociti live-demo URL on `index.html` and `velociti.html` if the deployed site lives somewhere other than `https://mchenryspagg.github.io/velociti-bike/`
- [ ] Optional: add a profile photo to `assets/` and reference it in the hero
- [ ] Optional: custom domain (e.g. `henryokam.dev`) — add a `CNAME` file with the domain, then point a DNS `CNAME` record at `<your-user>.github.io`

## Adding a new project later

1. Copy `delta.html`, rename to `[project-slug].html`
2. Edit content
3. Add a new card in the "Other projects" grid on `index.html`
4. Commit + push — GitHub Pages updates automatically
