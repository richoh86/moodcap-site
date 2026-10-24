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

## v1.1 content (branch `v1.1`)

The 1.1.0 release adds a "New in 1.1" band (profiles and tones, card styles and
sizes plus the line sticker, widget and daily reminder, monthly recap) and a
"MoodCap Plus" pricing section to both marketing pages, a rewritten support FAQ
(Plus prices, trial, managing and restoring the subscription, tones, widget,
reminders) and privacy sections for profiles, the widget, reminders and Plus.
Only one consumable pack (30 lines) is mentioned; the 100 and 300 packs are gone.
Footers link Apple's standard EULA as Terms of Use.

Prices: EN page in US dollars ($2.99 / month, $17.99 / year with a 7-day trial on
yearly only, 30-line pack $0.99); KO page in won (₩5,500 / ₩29,000, pack ₩2,200).

`assets/v11/*.jpg|webp` are real app output too: card renders (Film, Minimal,
4:5, 1:1, sticker, widgets, recap) and simulator screenshots of the 1.1 build,
downscaled to 540 px wide for cards and 440 px for phone screenshots. The
paywall screenshot is Korean, so it appears on the KO page only.

**Merge `v1.1` into `main` only after 1.1.0 is live on the App Store.** Until
then the live site must keep describing 1.0.x, which has no subscription.

## App Store links

Every App Store button uses the campaign-tagged link, so installs that came from
the site can be told apart in App Analytics:

```
https://apps.apple.com/app/apple-store/id6801974284?pt=119467638&ct=site&mt=8
```

Current product images: assets/release-1.2.3/{en,ko}/, rendered or captured from release 1.2.3 build 27 with sample data. Old cards/v11 images have been removed.
