# hold-website

Static site for Hold (the one-second game): landing page + the support and
privacy URLs required by App Store Connect.

Published via GitHub Pages: Settings → Pages → deploy from `main`, root folder.

Custom domain: **playhold.app** (set via the `CNAME` file). DNS must point the
apex at GitHub Pages (A records to 185.199.108–111.153, or an ALIAS/ANAME to
`<user>.github.io`). `.app` is HSTS-preloaded, so enable **Enforce HTTPS** in
the Pages settings once the domain resolves.

- `index.html` — landing / support page
- `privacy.html` — privacy policy ("collects nothing")
- `style.css` — tokens mirrored from the app's `Theme.swift`
- `icon.png` — app icon (source of truth: the app repo's asset catalog)
