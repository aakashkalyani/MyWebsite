# aakashkalyani.com

A modern, static personal website — one `index.html` file, no build step, no framework.
Light/dark mode, responsive, and fast. Content matches the previous Google Sites version.

```
aakash-website/
├─ index.html        ← the whole site (edit this to add papers/links)
├─ assets/
│  └─ photo.jpg      ← your headshot (see step 1)
├─ CNAME             ← custom domain for GitHub Pages
└─ README.md         ← this file
```

## 1. Add your photo (30 seconds)

The site shows a monogram “AK” until you add a photo.

1. Open your current site, right-click your headshot → **Save Image As…**
2. Save it into the `assets/` folder, named exactly **`photo.jpg`** (a square ~600×600 crop looks best).

Reload `index.html` — the photo replaces the monogram automatically. (No photo = the monogram stays; nothing breaks.)

## 2. Preview locally

Just double-click `index.html` — it opens in your browser. That’s the finished site.

## 3. Publish — keeping aakashkalyani.com

Two free options. Pick one.

### Option A — Netlify (easiest, no terminal)
1. Go to app.netlify.com → sign up (free).
2. Drag the **`aakash-website` folder** onto the Netlify dashboard. You get a live URL instantly.
3. **Domain settings → Add custom domain →** `aakashkalyani.com`. Netlify shows the exact DNS records to set.
4. At your domain registrar (wherever you bought aakashkalyani.com), replace the current Google records with Netlify’s. HTTPS is automatic.

### Option B — GitHub Pages (free forever, standard for academics)
1. Create a free account at github.com.
2. New repository → make it **Public** (name it anything, e.g. `website`).
3. **Add file → Upload files →** drag in `index.html`, the `assets` folder, and `CNAME`. Commit.
4. **Settings → Pages →** Source = `main` branch, `/root`. Save.
5. **Settings → Pages → Custom domain →** `aakashkalyani.com`. Tick **Enforce HTTPS**.
6. At your registrar, point DNS at GitHub:
   - Four `A` records for the apex `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record: `www` → `YOUR-USERNAME.github.io`
   - Remove the old Google Sites records.

DNS can take a few minutes to ~24h to propagate.

> **Keep Google Sites live** until the new site resolves, then switch the domain. Zero downtime, easy rollback.

## 4. Updating the site later

Everything is in `index.html`. To add a paper, copy an existing `<article class="paper">…</article>` block and edit the title, link, authors, and abstract. Status badges:
- `<span class="badge rr">R&amp;R · Journal</span>` — revise & resubmit
- `<span class="badge pub">Journal Name</span>` — published
- `<span class="badge status">Submitted</span>` — any status note

Resource buttons are just links: `<a href="URL" target="_blank" rel="noopener">Label</a>` inside `<div class="links">`.
