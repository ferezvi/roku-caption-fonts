# roku-caption-fonts

Subseted open-source fonts for Roku closed caption FCC compliance. Covers all 8 EIA-708 font styles with Latin character support verified on Roku OS.

## Background

The FCC requires that closed caption decoders support the 8 font styles defined in EIA-708. Roku OS exposes its own system fonts for sans-serif styles, but does not provide serif, monospace serif, cursive, or casual fonts. This repository provides subseted open-source fonts to fill those gaps.

All fonts have been subseted to the exact Unicode codepoints confirmed to render correctly on Roku OS, keeping file sizes minimal.

## FCC EIA-708 Font Coverage

| FCC Style | Font | Files | Notes |
|---|---|---|---|
| Proportionally spaced sans-serif | Noto Sans | Regular, Bold, Italic, BoldItalic | |
| Proportionally spaced serif | Noto Serif | Regular, Bold, Italic, BoldItalic | |
| Monospaced sans-serif | Noto Sans Mono | Regular, Bold | No italic variant exists |
| Monospaced serif | Courier Prime | Regular, Bold, Italic, BoldItalic | |
| Casual | Fredoka | Regular | |
| Cursive / Script | Dancing Script | Regular | |
| Small caps | — | — | Handled by Roku OS — no TTF needed |
| Default | — | — | Uses the regular variant of the loaded fallback font |

## Character Coverage

Fonts are subseted to Unicode codepoints confirmed to render on Roku OS, covering:

- **Latin-1** (U+0020–U+00FF) — Basic Latin, accented characters
- **Latin Extended-A/B** (U+0100–U+024F) — Additional European characters
- **General Punctuation** (U+2000–U+206F) — Typographic quotes, dashes, ellipsis
- **Currency Symbols** (U+20A0–U+20CF) — €, £, ¥ and others
- **Letterlike Symbols** (U+2100–U+214F) — ™, ©, ®
- **Mathematical Operators** (U+2200–U+22FF) — ±, ×, ÷, ≠ and others
- **Miscellaneous Symbols** — ★, ☆, ♪, ♫

Total: **344 codepoints** verified on Roku OS.

## Usage with Jellyfin

These fonts are intended to be used as Jellyfin fallback fonts, which are served to Roku clients for subtitle rendering.

### Installation

1. Download all fonts: [roku-caption-fonts.zip](./roku-caption-fonts.zip)
2. Extract and copy all `.ttf` files to your Jellyfin fallback font folder path
3. In the Jellyfin Dashboard, go to **Playback → Transcoding**
4. Set the **Fallback Font Path** to the folder where you copied the fonts
5. Enable **Enable Fallback Fonts**

For more details on Jellyfin font configuration, see the [official documentation](https://jellyfin.org/docs/general/administration/configuration/#fonts).

## Font Licenses

All fonts are licensed under the [SIL Open Font License 1.1](https://scripts.sil.org/OFL). Each font folder contains its own `OFL.txt` file.

| Font | Author | License |
|---|---|---|
| Noto Sans | Google | OFL 1.1 |
| Noto Sans Mono | Google | OFL 1.1 |
| Noto Serif | Google | OFL 1.1 |
| Courier Prime | Alan Dague-Greene | OFL 1.1 |
| Dancing Script | Impallari Type | OFL 1.1 |
| Fredoka | Milena Brandão et al. | OFL 1.1 |

## Related

- [Roku Font node documentation](https://developer.roku.com/dev/docs/font)
- [Roku Closed Caption documentation](https://developer.roku.com/dev/docs/closed-caption)
- [FCC Closed Captioning Display Requirements](https://www.fcc.gov/consumers/guides/closed-captioning-display-requirements-equipment)
- [EIA-708 / CTA-708 standard](https://en.wikipedia.org/wiki/CTA-708)
- [Jellyfin Font Configuration](https://jellyfin.org/docs/general/administration/configuration/#fonts)
