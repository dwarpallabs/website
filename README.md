# dwarpallabs.com

Static site for Dwarpal Labs, deployed by Cloudflare Pages on every push to `main`. Plain HTML and CSS, no build step, no JavaScript, no analytics.

Looks and wording match the LinkGuard app: the same colours, type scale, spacing and words. Change them in the app and here together.

- `index.html` — Dwarpal Labs home page; its LinkGuard card leads to the product page
- `linkguard/index.html` — LinkGuard product page (hero, how it works, what it warns about, privacy in plain words, languages)
- `linkguard/privacy.html` — LinkGuard privacy policy (linked from the Play Store listing)
- `404.html` — page-not-found page (Cloudflare Pages serves it for unknown addresses)
- `images/warning-screen.avif` / `.png` — the app's warning screen for the product page; AVIF first, PNG fallback. Retake from the app when the screen changes
- `_headers` — security headers applied by Cloudflare Pages
- `og-linkguard.png` — 1200×630 link-preview card (Open Graph / Twitter) shown when the site is shared; drawn from the app's icon geometry like `docs/play/make_assets.py` in the linkguard repo
- `fonts/` — tiny Noto Sans subsets (SIL OFL, `fonts/OFL.txt`) for the Ol Chiki and Meetei Mayek language names, which many computers can't display. Regenerate with `pyftsubset <font> --text='<names>' --flavor=woff2` if the names change
- `style.css` is cached by browsers for up to 4 hours, so the pages link it as `/style.css?v=N`. Bump `N` in every page whenever `style.css` changes, or visitors get the new HTML with the old styles.
- `favicon.svg`, `favicon.ico` (16/32/48 px), `apple-touch-icon.png` (180 px) — the LinkGuard shield, drawn from the app's launcher icon geometry (same code as `docs/play/make_assets.py` in the linkguard repo)
