# Atelier — landing page handoff

This bundle contains the **production-ready static landing page** for Atelier. Drop these files into the `slubrano-prog/Atelier` GitHub repo and Vercel will deploy it.

## What's in this folder

```
atelier-prod/
├── index.html       ← the page (Tweaks panel already removed)
├── styles.css       ← all styles
├── img/             ← studio photography (14 images)
├── vercel.json      ← Vercel routing config
└── .gitignore
```

## Baked-in defaults

The HTML ships with these locked defaults (set on `<body>`):

- **Theme:** `ivory`
- **Accent:** `magenta` (#B0185A)
- **Type pairing:** `serif-sans` (Instrument Serif + Geist)

The Tweaks panel and its JS have been removed — this is the clean public version.

## Deploy flow

1. Commit these files into the root of `slubrano-prog/Atelier` (or under `site/` if you prefer).
2. In Vercel: **Add New Project → Import** `slubrano-prog/Atelier`.
3. Framework Preset: **Other**. Root Directory: `./` (or `site/` if nested).
4. Deploy. Live in ~30 seconds.
5. Every `git push` to main → auto-deploy.

## Forms

All three forms (artist / landlord / investor) submit via `mailto:slubrano@stanford.edu` — the user's mail client opens with the body pre-filled.

To upgrade to a real backend later:
- **Formspree:** replace each form's `action` with your Formspree URL and remove the JS submit handler.
- **Custom endpoint:** replace the `mailto:` block in `index.html` with `fetch('/api/waitlist', ...)`.

## Notes

- No build step. No framework. Pure HTML/CSS/JS.
- Fonts loaded from Google Fonts.
- All `<img>` paths are relative (`img/...`) — they resolve from wherever you put the `index.html`.
