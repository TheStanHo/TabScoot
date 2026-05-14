# Tab Scoot — GitHub Pages site

Static **HTML + CSS** marketing site: **home** (`index.html`) with hero, feature grid, **screenshots** from the same images as `store-assets/chrome-web-store/`, a **privacy teaser**, and the full **`privacy.html`** policy.

## Quick setup

1. Create a **new public** GitHub repository (example name: `tabscoot-site`).
2. Copy **this entire folder** into that repo’s **root** (including `assets/`, `.nojekyll`, HTML, CSS, README).
3. GitHub: **Settings → Pages → Source**: branch **`main`**, folder **`/` (root)**.
4. Site URL examples:
   - `https://<username>.github.io/<repo>/` (project site)
   - `https://<username>.github.io/` (user site, if repo is `<username>.github.io`)

Use **`…/privacy.html`** as the Chrome Web Store **Privacy policy URL** (or the homepage if you prefer).

## Syncing screenshots from the extension repo

Images under `assets/screenshots/` and `assets/promo/` are **copies** of `store-assets/chrome-web-store/` so GitHub Pages does not depend on another repo path. After you update store screenshots, refresh the copies from the **ChromeExtension** repo root:

```powershell
Copy-Item "store-assets\chrome-web-store\screenshots\*.png" "tabscoot-site\assets\screenshots\" -Force
Copy-Item "store-assets\chrome-web-store\promotional\*.png" "tabscoot-site\assets\promo\" -Force
```

Then commit and push the **tabscoot-site** repo.

## Before you publish

- **`index.html`**: Keep the **Chrome Web Store** button URL aligned with the published listing.
- **`privacy.html`**: Keep text aligned with **`PRIVACY.md`** in the extension repo and with the **Privacy practices** tab in the developer dashboard (they must match behavior).
- **Open Graph**: `og:image` is a relative path (`assets/promo/...`). For best social previews after deploy, you may switch it to the **full HTTPS URL** of that image on your live site.

## Relationship to a private extension repo

The extension codebase can stay **private**. This site repo only needs public **marketing + privacy** pages.
