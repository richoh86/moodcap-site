# MoodCap: Vibe Camera & Diary — website

The marketing, support and privacy pages App Store Connect points at,
served by GitHub Pages from `main`. Public only because Pages requires it.

- `index.html` — Marketing URL (English; the `marketing_url` for all 39 storefronts)
- `ko/index.html` — Korean marketing page (무드캡 — 속마음 카메라 일기)
- `support.html` — Support URL
- `privacy.html` — Privacy Policy URL
- `assets/` — card images, favicons, Open Graph image

No build step, no framework, no JavaScript: each page carries its own CSS.

## Assets

`assets/cards/{en,ko}/*.jpg|webp` are **real app output**, not mockups. They are
rendered headlessly by `CardRenderer` / `PaletteCardRenderer` in the app repo
against `Resources/Demo/{solo,dog,duo}.jpg`, at 1080×1920, then downscaled to
540×960 for the web. The Korean set comes from the same render run with the
simulator language set to `ko`. Re-render them from the app repo when the card
layout or the brand bar changes.

Brand colours are copied from `Sources/App/BrandTheme.swift`:
ink `#14120F`, raised surface `#221E19`, subtitle yellow `#F5C84B`.

## App Store links

Every App Store button uses the campaign-tagged link, so installs that came from
the site can be told apart in App Analytics:

```
https://apps.apple.com/app/apple-store/id6801974284?pt=119467638&ct=site&mt=8
```
