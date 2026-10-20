# 30-Day Basic Azure Learning Workshop — Deploy Guide

**Author:** Dr. Sivakumar Madesan
**Package contents:** `index.html` (the complete workshop — single self-contained file, no build step),
`LICENSE.txt` (usage terms), this README.

Just upload the files to any static host. No server, database, or build pipeline required.
Learner progress is saved in the browser's own `localStorage` — nothing is sent anywhere.

---

## Option A — GitHub Pages (recommended)

1. Create a new **public** repository (e.g. `azure-workshop`).
2. Upload `index.html` (as `index.html` in the repo root), `LICENSE.txt`, and this `README.md`.
   - Web: repo page → *Add file → Upload files*.
   - CLI: `git clone <repo-url>`, copy the files in, `git add .`, `git commit -m "Publish workshop"`, `git push`.
3. Repo **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → **Save**.
4. Your workshop is live in ~1 minute at `https://<username>.github.io/azure-workshop/`.

## Option B — Netlify

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag the unzipped folder (containing `index.html`) onto the page.
3. You instantly get a public `https://<random-name>.netlify.app` URL — rename it under
   *Site settings → General → Site details* if you like.
4. (Optional) For continuous deploys, connect the folder to a Git repo instead: *Add new site →
   Import an existing project*.

## Option C — Azure Static Web Apps

1. In the [Azure portal](https://portal.azure.com), create a **Static Web App** (Free plan is enough).
2. Deployment source: **GitHub** (or *Other* to upload later). Authorize and pick your repo/branch.
3. Set **App location** to `/` (the folder containing `index.html`), leave API/Output empty → **Review + Create**.
4. Azure creates a GitHub Actions workflow; the site deploys automatically to a
   `https://<name>.azurestaticapps.net` URL shown on the resource overview page.

---

## Customizing

- **Title/author/license text:** edit the `<div class="cover">` block and the `<footer>` in `index.html`.
- **Colors:** all theme values live in the `:root` block at the top of the `<style>` section
  (`--azure`, `--teal`, `--ink`, …).
- **Resetting learner progress:** the page has a built-in *Reset progress* button (top-right).

## License summary

Free for personal learning. Commercial use (paid training, corporate workshops, redistribution
for profit) requires prior written permission — contact **inventsiva@gmail.com**.
See `LICENSE.txt` for the full terms.
