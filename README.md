# Staytus Collection — homepage demo

A showcase build of the Staytus Collection homepage, finished from the completed Claude Design
artboards and published as a live one-page demo.

**Live:** https://zubairthecreator.github.io/staytus-collection-demo/

## What this is

A **concept demo**, not the client's live site. It carries `noindex, nofollow` and a
`Concept demo — STB Studios` marker in the footer so it can never be mistaken for, or compete
with, Staytus Collection's own website.

## Build

Static. One `index.html` (tokens, styles and behaviour inlined) plus `assets/`. No build step,
no dependencies, no tracking scripts. Open the file, or serve the folder:

```bash
python -m http.server 8000
```

## Structure

Hero (animated entrance) → Welcome → Statement band → What We Offer → Portfolio → Contact.

The hero stage plays once per session: the building slides in from the right, the wordmark
travels out from behind it, the nav drops, then the tagline settles. Scroll is held for the
~2.3s the sequence runs and released after. Returning visitors in the same session get the
settled pose immediately; **Replay** re-runs it on demand. Under
`prefers-reduced-motion: reduce` nothing animates and scroll is never held.

## Design notes

Copy, contact details, project names and the disclaimer are the client's own and were not
altered. Style is the layer that changed:

- Every colour, size, space and duration binds to a `--*` token in `:root`. No stray hex.
- Two typefaces: Cormorant Garamond (display) and Work Sans (body/UI), replacing the mixed
  Inter/Work Sans pairing.
- One gold accent (`#D2A83E`), one job per component region. Navy and slate stay chrome.
- Motion is functional only — hover, press, focus, the scroll cue and the one hero entrance.
- Semantic landmarks, a single `h1`, skip link, visible focus rings, labelled form fields.
- `LocalBusiness` JSON-LD built from the NAP already on the page.

## Honest gaps

- **Portfolio photography is missing.** The three project tiles are branded placeholders, not
  invented imagery. Drop real photos in and swap the tile markup.
- **The enquiry form has no backend.** Submitting says so plainly and points at the real phone
  and email rather than faking a success state.

## Assets

Sources came from the design export at 25 MB; shipped here at ~0.7 MB as WebP.

| File | Role |
|---|---|
| `assets/building.webp` | Rouxcor House, 20 Herold Street — hero subject |
| `assets/sky.webp` | Masked backdrop behind the hero |
| `assets/wordmark.webp` | Staytus Collection wordmark |
| `assets/mark.webp` | SC monogram — nav, seal, portfolio tiles |
| `assets/og.jpg` | Link-preview card |
| `assets/favicon.png` | Tab icon |
