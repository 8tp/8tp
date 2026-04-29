# Codex prompt — GitHub profile README banner

Hand this entire file to **codex**. Use codex's built-in image-generation
skill, calling **`gpt-image-2`** (not `gpt-image-1`). The API surface is
identical to `gpt-image-1`, but quality and text rendering are noticeably
better, so do not silently downgrade.

## Goal

Generate **one** image at `assets/banner.webp` (1280×320, 4:1) for the top
of the `8tp/8tp` GitHub profile README. The banner replaces the current
`assets/profile-header.svg` and must visually match the
[chuds.dev](https://chuds.dev) hero so my profile and site read as one
coherent rig.

## Hard constraints

### Palette — Tokyo Night, copied verbatim from `~/.config/kitty/kitty.conf`

```
bg          #1a1b26   (page background, terminal canvas)
bg-dark     #16161e   (deepest backdrop, title bars)
panel       #1f2335   (raised panels)
border      #3b4261   (1px window edges)
fg          #c0caf5   (primary text)
fg-dim      #a9b1d6   (secondary text)
fg-muted    #737aa2   (labels, helpers)
comment     #565f89   (the muted-most text)

red         #f7768e
orange      #ff9e64
yellow      #e0af68
green       #9ece6a
mint        #73daca
cyan        #7dcfff
blue        #7aa2f7
magenta     #bb9af7   (brand — yabai's insert-feedback color)
purple      #9d7cd8
```

- The **brand accent** is magenta `#bb9af7`. Secondary accent is cyan
  `#7dcfff`. No other accents on this banner.
- Allowed background is `#1a1b26` (base) on top of `#16161e` (deepest).
  Avoid pitch black (`#000`) and avoid bluish slate (`#2a3041`-ish).
- No warm browns, no tans, no orange-dominant tones, no synthwave neon,
  no glassmorphism, no glow halos. Tokyo Night is matte.

### Style

- **Flat modern UI.** Crisp 1px borders (`#3b4261`), soft shadows, generous
  padding, rounded corners 8–12 px. Think Linear / Raycast / Arc / Ghostty.
- **Typography inside the image:** chunky geometric monospace
  (JetBrains Mono / Berkeley Mono / PragmataPro feel) for the wordmark.
  Real, fully-rendered English. **No garbled glyphs, no half-letters, no
  question marks where letters should be, no "tex̸t̷" smearing.** If a
  label can't render cleanly, leave it out — never ship corrupted typography.
- **No human faces**, no fake brand logos, no pixelation, no blurry text,
  no AI signatures.

### Output sizing

- Generate at **1024×1024**, then center-crop to **1024×256** and resize
  to **1280×320** (4:1). WebP, quality 85, method 6.
- Save to `assets/banner.webp` in this repo.

---

## The banner

```
A wide horizontal banner image, 4:1 aspect ratio (1280×320), Tokyo Night
theme. The whole banner reads as a flat, deliberate, terminal-adjacent
piece of typographic art — as if it's the title bar of one big kitty
window pinned to the top of a GitHub profile.

Background: solid #1a1b26 (Tokyo Night base) with a single very faint
diagonal grain texture, almost imperceptible. Two extremely low-opacity
radial washes for depth — magenta #bb9af7 in the top-left corner, cyan
#7dcfff in the bottom-right. Both kept so faint the canvas still reads
as nearly flat. No gradient skies, no glow halos.

Centered horizontally, occupying ~55% of the canvas width: the wordmark
"Hunter / 8tp" rendered in chunky geometric monospace, weight 700–900,
all lowercase except the capital "H". Letter-spacing slightly tight
(around 0.02em). The "Hunter" portion is in #c0caf5 off-white. The "/"
separator is in green #9ece6a — a unix path divider. The "8tp" portion
is in magenta #bb9af7 with a subtle 1px inner shadow giving it a slight
pressed-in look. Optional: a thin 1px magenta cursor block blinking
after "8tp".

Below the wordmark, in a smaller weight-400 monospace with the same
letter-spacing, a single tagline line:
    $ shipping web apps, multiplayer systems, and macOS tools
The "$" prompt symbol is in green #9ece6a. The rest of the tagline is
in #a9b1d6 muted lavender.

In the very bottom-left corner, three traffic-light dots (red #f7768e,
yellow #e0af68, green #9ece6a) the size of pencil erasers — a hint that
the whole thing is a kitty terminal window. In the top-right corner, a
faint label "~/profile" in #565f89 monospace.

Absolutely no human faces, no decorative scenes, no characters, no
glow halos, no synthwave neon, no realism. Sharp, legible vector-flat
typography. No anti-aliasing artifacts on text.
```

Crop: 1024×1024 → center-crop to 1024×256 → resize to 1280×320.

---

## Implementation

Use codex's built-in image-generation skill with model **`gpt-image-2`**.
The shape of the call is identical to `gpt-image-1`:

```python
from openai import OpenAI
import base64, pathlib, subprocess

client = OpenAI()

resp = client.images.generate(
    model="gpt-image-2",
    prompt=BANNER_PROMPT,   # the prompt block above, verbatim
    size="1024x1024",
    quality="high",
    n=1,
)

png = pathlib.Path("/tmp/banner.png")
png.write_bytes(base64.b64decode(resp.data[0].b64_json))

out = pathlib.Path("assets/banner.webp")
out.parent.mkdir(parents=True, exist_ok=True)
subprocess.check_call([
    "magick", str(png),
    "-gravity", "center",
    "-crop", "1024x256+0+0", "+repage",
    "-resize", "1280x320",
    "-quality", "85",
    "-define", "webp:method=6",
    str(out),
])
```

If `magick` isn't on the path, fall back to `ffmpeg` or `sharp` — anything
that produces a correctly-sized webp at quality 85.

## After it lands

1. Open `assets/banner.webp` and visually confirm:
   - "Hunter / 8tp" renders cleanly with no garbled glyphs.
   - The "$" prompt and tagline are fully legible.
   - Background is Tokyo Night navy, NOT brown / tan / black / slate.
   - Traffic-light dots are bottom-left.
2. If anything is off (corrupted text, off-palette art, layered elements
   colliding), regenerate up to **3 times** before falling back to the
   existing `assets/profile-header.svg`. Do not ship gibberish typography.
3. Don't commit yet — leave the new banner staged so I can review it
   before it goes into the README rewrite.

## Sanity rules

- Estimated cost: 1 image × `gpt-image-2 high` ≈ $0.05–$0.09. If the API
  returns a content-policy refusal, soften wording (e.g. "combat" →
  "match") and retry once.
- If `gpt-image-2` is not yet exposed by the OpenAI API key in use, **stop
  and tell me** rather than silently calling `gpt-image-1`. I want the
  newer model specifically.
