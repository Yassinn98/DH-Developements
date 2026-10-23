# DH Developments website

Static single-page site (HTML + CSS + vanilla JS, no build step). Works on GitHub Pages as-is.

## Publish on GitHub Pages
1. Create a new repository on GitHub (e.g. `dh-developments`).
2. Upload everything in this folder to the repository root: `index.html`, the `images/` folder, `.nojekyll` and `README.md`.
   - Web upload: **Add file → Upload files**, drag the contents in, then **Commit changes**.
   - Or with git: `git init && git add . && git commit -m "Add website" && git branch -M main && git remote add origin <repo-url> && git push -u origin main`
3. In the repo go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then **Save**.
4. After a minute the site is live at `https://<username>.github.io/<repo>/`.

Pages are routed with `#/…` hashes, so no server configuration is needed. A custom domain can be added under Settings → Pages.

## Editing content
Everything editable is at the top of the `<script>` in `index.html`:
- `SITE` – phone, email, WhatsApp number, address, Facebook link, map location.
- `PROJECTS` – Vera and The Villa (copy, unit types, amenities, gallery, payment plan, status).
- `NEWS`, `STATS`, `TEAM`, `RANGE` – home and about page content.
- `STR` – all interface text (English and Arabic).

## Images
All images are in `images/` and listed by key in the `IMG` block at the bottom of `index.html`.
To replace one, overwrite the file (same name) or change its path in the `IMG` block.
If you replace a floor plan, master plan or map with a different shape, update its `[width, height]` in `IMGDIM` just below.

## Still to fill in
- Real phone, email, WhatsApp number and office address (`SITE`).
- Vera's own images and copy (currently The Villa renders stand in).
- Leadership team names and photos (`TEAM`).
- Payment plan details per project (`payment` in `PROJECTS`).
- The contact and registration forms validate but do not send anywhere yet: add your form service or backend at the `TODO` in `bindForm()`.
