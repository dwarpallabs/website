# dwarpallabs.com

Static site for Dwarpal Labs, deployed by Cloudflare Pages on every push to `main`. Plain HTML and CSS, no build step, no JavaScript, no analytics.

Looks and wording follow the shared design system in [`linkguard/docs/design-system.md`](https://github.com/dwarpallabs/linkguard/blob/main/docs/design-system.md): the same colours, type scale, spacing and words as the app. Change a token there first, then here.

- `index.html` — home page
- `linkguard/privacy.html` — LinkGuard privacy policy (linked from the Play Store listing)
- `_headers` — security headers applied by Cloudflare Pages
- `fonts/` — tiny Noto Sans subsets (SIL OFL, `fonts/OFL.txt`) for the Ol Chiki and Meetei Mayek language names, which many computers can't display. Regenerate with `pyftsubset <font> --text='<names>' --flavor=woff2` if the names change
- `style.css` is cached by browsers for up to 4 hours, so the pages link it as `/style.css?v=N`. Bump `N` in every page whenever `style.css` changes, or visitors get the new HTML with the old styles.
- `favicon.svg`, `favicon.ico` (16/32/48 px), `apple-touch-icon.png` (180 px) — the LinkGuard shield, drawn from the app's launcher icon geometry (same code as `docs/play/make_assets.py` in the linkguard repo)
