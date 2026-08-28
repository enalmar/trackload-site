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
- `assets/` — icon, screenshots and the Open Graph card, generated from the app

Screenshots and the Open Graph card are produced from the app itself by
`Tools/GenerateScreenshots.swift` and `Tools/GenerateOpenGraph.swift` in the app
repository, not edited by hand.
