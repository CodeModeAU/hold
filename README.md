# hold-website

Static site for Hold (the one-second game): landing page + the support and
privacy URLs required by App Store Connect, at **playhold.app**.

Built with [Vite](https://vitejs.dev): `npm install && npm run build` outputs
both pages to `dist/`. `npm run dev` for local development.

## Hosting

**Primary: Vercel** — this repo (Bitbucket `codemodeau/hold-website`) is
connected to the `hold-website` Vercel project; pushes to `main` deploy
automatically. The Vite framework preset is auto-detected; clean URLs
(`/privacy` instead of `/privacy.html`) come from `vercel.json`.
DNS: apex A record → `76.76.21.21`, `www` CNAME → `cname.vercel-dns.com`.

**Fallback: GitHub Pages** — a flat (pre-Vite) copy of the site lives in
[`CodeModeAU/hold`](https://github.com/CodeModeAU/hold) and serves from the
`main` branch root with the custom domain set via its `CNAME` file.
DNS: apex A records → 185.199.108–111.153, `www` CNAME →
`codemodeau.github.io`. `.app` is HSTS-preloaded, so Enforce HTTPS must be on
(the Let's Encrypt cert is issued automatically once DNS resolves).

Switching hosts is purely a DNS change in Route 53 — both stay deployable.

## Files

- `index.html` — landing / support page
- `privacy.html` — privacy policy ("collects nothing")
- `style.css` — tokens mirrored from the app's `Theme.swift` (bundled by Vite)
- `public/` — assets copied verbatim to the output root (app icon, App Store
  badge, `CNAME`); icon source of truth is the app repo's asset catalog
