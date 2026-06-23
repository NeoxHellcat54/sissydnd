# Dressed & Dared — v5 single-file GitHub build

This build is intentionally simple to avoid GitHub Pages upload/caching problems.

## Upload instructions

Upload only these files to the root of your GitHub repository:

- `index.html`
- `.nojekyll`
- `README.md` optional

There are no icons, no manifest, no service worker, no external JavaScript, and no external CSS in this build. The whole app is inside `index.html`.

## Why this build exists

Earlier builds included app icons and PWA files. If one of those PNG icon files is accidentally uploaded or renamed as `index.html`, GitHub Pages will show text beginning with `PNG IHDR`, which means the site is serving an image file as the page.

This version removes those extra files so there is nothing to mix up.

## If GitHub still shows the old/broken page

1. Delete every old file in the repository.
2. Upload the v5 files.
3. Commit changes.
4. Open the site with `?v=5` added to the URL.
5. Hard refresh.
6. If needed, open browser DevTools → Application → Service Workers → Unregister.

## App rules included

- Neon Dressing Room theme
- Local storage only
- Hard-coded wardrobe categories with color checkboxes
- Skip categories with no checked color
- Fully random user-filled locations
- Fully random user-filled dares
- User chooses dare count
- No duplicate dares in the same roll
- Exhys rewards weighted 30–70 per dare
- Shop with themes, roll effects, and full outfits
- Outfit rarities
- Global shop price inflation: base price × 1.1^totalPurchases, rounded up to 1 decimal
