# trackload-site

The website for Trackload, an iOS barbell program tracker: a marketing page, a
privacy policy and a support page. This repository is the website only — the
app's Swift source is not here.

Three static files, all CSS inline, no build step and no dependencies, so it
still works in three years when nobody has run an install command in it.
Published with GitHub Pages from `main` at the repository root.

- `index.html` — what the app is
- `privacy.html` — linked from the App Store listing, and required for it
- `support.html` — likewise
- `assets/` — the icon, the Open Graph card and `shots/`, the screenshots

The screenshots are real captures of the app, not mock-ups: the iPhone 17 Pro
Max simulator running `-demo`, once in light and once in dark, with the status
bar set to 9:41. The LLM sequence is one real change carried through the app —
the request typed into Copy for LLM, a reply pasted back, its review, then
Today after Apply. Each capture is scaled to 720 px wide and saved as a JPEG; the page picks
light or dark with `prefers-color-scheme`.

```bash
sips -Z 1564 capture.png --out name-light.png
sips -s format jpeg -s formatOptions 86 name-light.png --out name-light.jpg
```

Not AVIF from `sips`: macOS writes a tiled AVIF carrying an HDR `clli`
property that Firefox's parser rejects, and since Firefox does support AVIF
a `<picture>` never falls back to the JPEG — the screenshot is simply
missing. Check any new image format in Firefox before using it here.

The Open Graph card is made by `Tools/GenerateOpenGraph.swift` in the app
repository from the icon and the light review capture, not edited by hand.
The App Store frames are `Tools/GenerateScreenshots.swift`, also there.
