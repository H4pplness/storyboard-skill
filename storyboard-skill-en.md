---
name: storyboard-poster
description: "Build prompt sets for short video storyboards. Use when the user wants a storyboard for food, character, product, process, or any short-form content needing scene-by-scene visualization. Default output: a storyboard poster prompt plus a video prompt for AI video apps (Seedance, Kling, Runway, Pika). If the user explicitly asks for a character reference sheet, prepend that prompt. Trigger on: storyboard, shot breakdown, scene planning, video prompt, short video, reel planning, shooting script, shot list, visualize a video concept."
---

# Storyboard Poster Skill

Produces up to three prompt blocks the user can paste into image / video AIs:

1. **Character Reference Sheet** — only when the user asks for one
2. **Storyboard Poster** — always produced (16:9 infographic, multi-panel)
3. **Video Prompt** — always produced (Seedance / Kling / Runway / Pika)

Default behavior: produce blocks 2 and 3. Add block 1 only on explicit request.

---

## Block 1 — Character Reference Sheet Prompt *(on request only)*

A single landscape image containing: hero pose · front/side/back turnarounds · 2 detail crops (face + costume) · expression chart (4+ bust portraits) · footer strip (palette + materials + tagline). Same render style as the storyboard.

Template:

```
Create a professional character reference sheet as a single cohesive poster.
Format: landscape, [BACKGROUND], thin black borders between zones, bold sans-serif labels.
ONE single image — do not split into separate images.

STYLE: [RENDER_STYLE — e.g. Pixar 3D stylized / hyper-realistic / anime cel-shaded /
flat vector / Ghibli hand-painted]
Lighting: [studio soft-box / overhead spot / natural window]

CHARACTER:
• Name: [name]
• Age & build: [age, gender, build]
• Skin tone: [specific descriptor]
• Hair: [color, length, style]
• Eyes: [color + quality]
• Signature feature: [one identifier]
• Costume: [top to bottom with materials and colors]
• Color palette: [4–6 colors, hex preferred]

ZONES:
• Hero pose: full-body 3/4 view (30°), pose relevant to the video concept
• Turnarounds: front (0°) / side (90°) / back (180°), neutral A-pose, same scale,
  guide lines at crown/shoulder/hip/heel
• Detail crops: (1) face — signature feature + skin texture; (2) costume — fabric + key accessory
• Expression chart: [N≥4] bust portraits, 3/4 angle, identical lighting,
  labeled with emotions matching the video's arc
• Footer strip: color swatches · material callouts · one-line tagline
```

Once generated, the user uploads the sheet as an image reference for the storyboard image gen.

---

## Block 2 — Storyboard Poster Prompt

Template:

```
Create a crisp infographic storyboard poster.
Layout: wide 16:9, white background, black borders, bold black typography.
Render style: [RENDER_STYLE — must match the reference sheet if one exists]

[IF reference sheet exists, include:]
CHARACTER CONSISTENCY: All panels featuring [name] must match the attached reference
sheet exactly — same hair, skin, costume, signature feature. Use the hero pose as anchor.

HEADER:
• Title in ALL CAPS
• TOTAL VIDEO TIME: [Y] SECONDS
• [N] SHOTS · [mood word 1] · [mood word 2] · [mood word 3]
• Legend row: [4 short icon labels relevant to the video — see legend guidance below]

COMMON BRIEF:
• Character: [one sentence — or "see attached reference sheet"]
• Setting: [location, props, lighting]
• Color palette: [4–7 colors, must match reference sheet]
• Tone: [2–3 keywords]
• Arc: [one sentence from X → Y]

PANELS:
Shot [N] — [scene name]:
[Main action]. [Color/texture detail]. [Character state if present]. [Arc role] [CAMERA]
...
Mark the climactic shot with ★.

FOOTER:
• VIDEO FLOW: [N] shots × ~[X]s = [Y]s. [One-sentence arc recap]
• CAMERA TIPS: [angles used and when]
• LIGHT & STYLE: [palette + lighting summary]
• DIRECTOR NOTES: [one creative sentence]
```

### Camera codes

| Code | Meaning |
|---|---|
| `[OVH]` | Overhead — straight down |
| `[LOW]` | Low angle — looking up |
| `[SIDE]` | Side profile — lateral |
| `[CLOSE]` | Tight close-up |
| `[POV]` | First-person view |

### Legend row guidance

Pick 4 short labels relevant to the video type:
- **Food/cooking**: `ACTION · HEAT · TIME · INGREDIENT`
- **Character**: `ACTION · EMOTION · LOCATION · MOMENT`
- **Product**: `FEATURE · ANGLE · CONTEXT · DETAIL`
- **Process**: `INPUT · STEP · TOOL · OUTPUT`

---

## Block 3 — Video Prompt (Seedance / Kling / Runway / Pika)

Template:

```
VIDEO PROMPT — [TITLE]

CHARACTER NOTE: [name] — [one sentence: hair + key costume + signature feature]
[Omit this line if no character]

STYLE & SETTING:
[1–2 sentences: location, render style, color tone, lighting]

SCENES:

Scene [N] — [name] (~[X]s):
Camera: [angle + movement, e.g. "low angle, slow push-in"]
Character: [state/expression — omit line if no character in this shot]
Action: [one sentence, strong active verb]
...
```

Rules: camera must include angle AND movement. Action uses specific verbs (slices, lifts, turns), never describes appearance. Scene durations must sum to the storyboard total.

---

## Quick variants

| Video type | Reference sheet? | Render style hint | Arc pattern |
|---|---|---|---|
| Character / narrative | On request | match personality | setup → signature action → reveal |
| Food / cooking | On request (only if chef's face shown) | Pixar 3D or hyper-realistic | raw → finished → first bite |
| Product | Skip | clean studio product photography | unbox → features → use → beauty |
| Process | Skip | flat vector infographic | problem → steps → result |

---

## Single checklist

- [ ] Shot count in header matches actual panel count
- [ ] Climactic shot marked with ★
- [ ] Each shot has: action + environment + character state (if present) + camera angle
- [ ] Color palette consistent across reference sheet (if used), storyboard panels, and video prompt
- [ ] If reference sheet used, `CHARACTER CONSISTENCY` block is in the storyboard prompt
- [ ] Video prompt: every scene has Camera + Action (+ Character if relevant) + duration
- [ ] Scene durations sum to total video time

---

## Example — The Sushi Chef (storyboard + video prompt)

### Storyboard Poster Prompt

```
Create a crisp infographic storyboard poster.
Layout: wide 16:9, white background, black borders, bold black typography.
Render style: premium Pixar 3D stylized.

HEADER:
• THE SUSHI CHEF
• TOTAL VIDEO TIME: 12 SECONDS
• 8 SHOTS · SHARP · PRECISE · HYPNOTIC
• Legend row: ACTION · HEAT · TIME · INGREDIENT

COMMON BRIEF:
• Character: young Japanese male chef, white double-breasted jacket, charcoal apron,
  white headband, short black hair, focused calm
• Setting: hinoki wood counter, bamboo rolling mat, warm overhead spot lighting
• Color palette: coral salmon · ivory rice · jade avocado · jet-black nori ·
  hinoki wood · soft ivory steam
• Tone: sharp · meditative · deeply satisfying
• Arc: raw rice to first bite — one roll, eight perfect pieces

PANELS:
Shot 1 — Rice fold: Hands fold steaming rice with bamboo paddle. Warm ivory. Calm opening. [OVH]
Shot 2 — Nori held up: Sheet held to light, jet-black and translucent. Graphic. [SIDE]
Shot 3 — Rice spread: Paddle drags rice across black nori. White on black contrast. [OVH]
Shot 4 — Fillings placed: Salmon, avocado, cucumber lined up. Most colorful panel. [SIDE]
Shot 5 — The roll: Bamboo mat presses forward, even pressure. Compression. [SIDE]
Shot 6 — The cut ★: Knife down, cross-section revealed — coral, jade, white, black. Hero. [LOW]
Shot 7 — The lineup: Eight pieces upright on hinoki board. Beauty shot. [OVH]
Shot 8 — The eat: Chef lifts piece, eyes close. Steam rising. Grace note. [CLOSE]

FOOTER:
• VIDEO FLOW: 8 shots × ~1.5s = 12 seconds. Rice to roll to silence.
• CAMERA TIPS: overhead for prep + lineup, low for the cut, side for roll, close for eat.
• LIGHT & STYLE: warm overhead spot, coral salmon, jade, white, jet-black, hinoki.
• DIRECTOR NOTES: one chef, one roll, eight perfect pieces.
```

### Video Prompt

```
VIDEO PROMPT — THE SUSHI CHEF

CHARACTER NOTE: Japanese male chef — short black hair, pristine white chef jacket
with charcoal apron, white headband across forehead.

STYLE & SETTING:
Pixar 3D stylized. Clean omakase counter with warm overhead spotlighting.
Ivory and coral tones, meditative atmosphere.

SCENES:

Scene 1 — Rice fold (~1.5s):
Camera: overhead, static
Action: Bamboo paddle folds steaming rice in wooden bowl

Scene 2 — Nori held up (~1.5s):
Camera: side profile, static
Character: focused, eyes locked on nori
Action: Chef holds nori sheet up to light, translucent against the spot

Scene 3 — Rice spread (~1.5s):
Camera: overhead, slow push-in
Action: Paddle drags rice across black nori in one clean motion

Scene 4 — Fillings placed (~1.5s):
Camera: side profile, static
Action: Chef places salmon, avocado, cucumber in precise row on the nori

Scene 5 — The roll (~1.5s):
Camera: side profile, static
Action: Bamboo mat presses forward, rolling tightly with even pressure

Scene 6 — The cut (~1.5s):
Camera: low angle, slow push-in
Character: intense concentration
Action: Knife comes down cleanly, cross-section of roll revealed

Scene 7 — The lineup (~1.5s):
Camera: overhead, slow pull-back
Action: Eight sushi pieces stand upright in a row on hinoki board

Scene 8 — The eat (~1.5s):
Camera: close-up, static
Character: quiet satisfaction, eyes close softly
Action: Chef lifts one piece slowly to his lips, steam rising
```