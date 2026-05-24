---
name: storyboard-poster-en
description: >
  Create a complete prompt to generate an infographic storyboard poster for short videos (under 60 seconds).
  Use when the user wants: a storyboard for food, product, character, process, or any short-form content
  that needs scene-by-scene visualization — characters are described directly in text, no existing prototype needed.
  After generating the storyboard, automatically generate a concise video prompt for AI video apps
  like Seedance, Kling, Runway, and Pika — including overall style/setting and per-scene camera + action descriptions.
  Output is: (1) storyboard prompt for image-gen AI, and (2) video prompt for video-gen AI.
  If the user already has a character prototype / concept sheet, use the character-prototype skill instead.
  Trigger whenever the user says: storyboard, shot breakdown, scene planning, video prompt, short video,
  reel planning, shooting script, shot list, or asks to visualize a video concept scene by scene.
---

# Storyboard Poster Skill (English)

This skill helps you build a prompt to generate an infographic storyboard poster —
16:9 wide layout, multi-panel, with header/footer containing cinematography notes.

Characters are described entirely in text inside the Common Brief.
If the user already has a character prototype, use the **character-prototype** skill instead.

---

## Prompt Structure — 3 Layers

```
[LAYER 1 — AI Instructions]
[LAYER 2 — Common Brief]
[LAYER 3 — Panel Descriptions]
```

---

## Layer 1 — AI Instructions

```
Create a crisp, clean infographic storyboard poster.
Layout: wide 16:9, white background, black borders, bold black typography.
Render style: [RENDER_STYLE] — see Common Brief for color palette.

Top header must include:
• Title of the video (in ALL CAPS)
• Total video time (e.g. TOTAL VIDEO TIME: 12 SECONDS)
• Shot count + 3 mood adjectives (e.g. 8 SHOTS · SHARP · PRECISE · HYPNOTIC)
• Legend icons row: ACTION · HEAT · TIME HINT · INGREDIENT

Each panel must include:
• Panel number and short title
• Main visual described in the panel
• 1–2 legend icon tags relevant to that shot

Footer must include:
• VIDEO FLOW: shot breakdown formula
• CAMERA TIPS: key angles used per shot type
• LIGHT & STYLE: color palette + lighting character
• DIRECTOR NOTES: one-line creative summary of the whole piece
```

> **`[RENDER_STYLE]`** — replace with your desired render style:
> `premium Pixar 3D stylized` · `flat vector illustration` · `hyper-realistic` ·
> `anime cel-shaded` · `minimal line art, monochrome`

---

## Layer 2 — Common Brief

```
COMMON BRIEF:
• Character: [gender, age, appearance, outfit, dominant expression]
• Setting: [location, fixed props, lighting style]
• Color palette: [4–7 dominant colors/materials]
• Tone & feel: [2–3 emotional keywords]
• Total duration: [N shots × ~Xs = Y seconds]
• Arc summary: [1 sentence emotional journey: from X → to Y]
```

---

## Layer 3 — Panel Descriptions

```
Shot [N] — [SCENE NAME]:
[Main action]. [Color/texture detail]. [Role in arc] [CAMERA ANGLE]
```

**Camera angle codes:**

| Code | Meaning |
|---|---|
| `[OVH]` | Overhead locked — straight down from above |
| `[LOW]` | Dramatic low angle — looking up |
| `[SIDE]` | Side profile — lateral view |
| `[CLOSE]` | Tight close-up — macro, fine detail |
| `[POV]` | Point of view — character's perspective |

---

## Pre-Send Checklist

- [ ] Shot count in header matches actual panel count
- [ ] At least 1 shot marked as "hero frame" / climax
- [ ] Arc summary accurately reflects journey from Shot 1 → Shot N
- [ ] Each shot has: action + environment detail + arc role + camera angle
- [ ] Common Brief includes: character · setting · color palette · tone · duration
- [ ] Colors in Common Brief match colors described in panels

---

## Bonus Step — Generate Video Prompt (Seedance / Kling / Runway / Pika)

After completing the storyboard prompt, **automatically generate a video prompt** for AI video apps.

> Goal: concise, clear prompt — enough for AI video to understand context, style, and action per scene.
> Focus on: **setting · visual style · camera · action**.

### Video Prompt Structure

```
VIDEO PROMPT — [VIDEO TITLE]

STYLE & SETTING:
[1–2 sentences: overall context, render style, color tone, dominant lighting]

SCENES:

Scene [N] — [SCENE NAME] (~[X]s):
Camera: [angle + movement]
Action: [description of the main action in this scene]

[Repeat for remaining scenes]
```

### Writing Guide

**STYLE & SETTING** (1–2 sentences):
- What the setting is, where it is, what time of day
- Visual style: `Pixar 3D` · `cinematic live-action` · `anime` · `flat 2D` · `hyper-realistic`
- Dominant color tone and lighting

**Camera** (concise):
- Angle: `overhead` · `low angle` · `side profile` · `close-up` · `POV`
- Movement: `static` · `slow push-in` · `tracking` · `pan left/right` · `tilt up/down`

**Action** (1 sentence, strong verbs):
- Describe the **main action** happening in the scene
- Favor specific verbs: `slices` · `walks forward` · `lifts` · `turns to face camera`

### Video Prompt Checklist

- [ ] STYLE & SETTING is brief — 2 sentences max
- [ ] Each scene has all 3 parts: Camera · Action · Suggested duration
- [ ] Camera includes both angle + movement
- [ ] Action uses specific verbs, describes **action** not appearance
- [ ] Total scene durations match the storyboard

---

## Variants by Video Type

### Food / Cooking Video
- Render style: `Pixar 3D` or `hyper-realistic`
- Arc: raw ingredients → finished dish → first bite
- Hero frame: the slice / plating moment / first bite

### Character / Character Showcase Video
- Render style: match the character's personality
- Arc: establish setting → signature action → emotional reveal
- Hero frame: close-up expression or signature move
- Note: if you need high character consistency with an existing design, use the **character-prototype** skill

### Product Showcase Video
- Render style: `clean studio product photography, white cyclorama`
- Character: optional — can use hands-only
- Arc: unboxing → features → in-use → beauty shot

### Process / How-It-Works Video
- Render style: `flat vector, bold outlines, infographic style`
- No fixed character needed
- Arc: problem → steps → result

---

## Full Example Prompt — The Sushi Chef

```
Create a crisp, clean infographic storyboard poster.
Layout: wide 16:9, white background, black borders, bold black typography.
Render style: premium Pixar 3D stylized.

Top header: • THE SUSHI CHEF • TOTAL VIDEO TIME: 12 SECONDS
• 8 SHOTS · SHARP · PRECISE · HYPNOTIC
• Legend icons: ACTION · HEAT · TIME HINT · INGREDIENT

---

COMMON BRIEF:
• Character: young Japanese male, short black hair, pristine white chef jacket,
  calm focused expression, always at the same omakase counter
• Setting: clean hinoki wood counter, bamboo rolling mat, warm overhead spot lighting
• Color palette: coral salmon · pure ivory rice · jade green avocado ·
  glossy jet-black nori · pale hinoki wood · soft ivory steam
• Tone & feel: sharp · meditative · deeply satisfying
• Total duration: 8 shots × ~1.5s = 12 seconds
• Arc: from raw rice to the first bite — one roll, eight perfect pieces

---

PANELS:

Shot 1 — Rice fold: Bamboo paddle mid-fold in wooden bowl, steam rising. Warm ivory tones. Calm opening. [OVH]
Shot 2 — Nori held up: Sheet held to light — jet black, translucent, glossy. Graphic and striking. [SIDE]
Shot 3 — Rice spread: Paddle dragging rice across black nori in one motion. White on black. Contrast shot. [OVH]
Shot 4 — Fillings placed: Salmon strips, avocado, cucumber lined up. Coral and jade — most colorful panel. [SIDE]
Shot 5 — The roll: Bamboo mat pressed forward, even pressure, mat texture visible. Compression. [SIDE]
Shot 6 — The cut ★: Knife down, cross-section revealed. Salmon coral · jade green · white rice · black nori. Hero frame. [LOW]
Shot 7 — The lineup: Eight pieces upright in a row on hinoki board. Overhead beauty shot, glistening. [OVH]
Shot 8 — The eat: Chef lifts piece, eyes close slowly. Quiet satisfaction. Steam rising. Closing grace note. [CLOSE]

---

Footer:
• VIDEO FLOW: 8 shots × ~1.5s = 12 seconds. Rice to roll to silence.
• CAMERA TIPS: overhead locked for rice + lineup, low angle for the cut, side for compression, close-up for eat.
• LIGHT & STYLE: warm overhead spot, coral salmon, jade green, pure white, jet-black nori, pale hinoki wood.
• DIRECTOR NOTES: one chef, one roll, eight perfect pieces. Sharp, calm, deeply satisfying.
```

---

## Full Example Video Prompt — The Sushi Chef

```
VIDEO PROMPT — THE SUSHI CHEF

STYLE & SETTING:
Pixar 3D stylized. Clean omakase counter with warm overhead spotlighting.
Warm ivory and coral tones, minimal background, calm and meditative atmosphere.

SCENES:

Scene 1 — Rice fold (~2s):
Camera: overhead, static
Action: Bamboo paddle folds steaming rice in wooden bowl, soft steam rises

Scene 2 — Nori held up (~1.5s):
Camera: side profile, static
Action: Sheet of nori held up to light, translucent and glossy, graphic contrast

Scene 3 — Rice spread (~1.5s):
Camera: overhead, slow push-in
Action: Paddle drags white rice across black nori in one clean motion

Scene 4 — Fillings placed (~2s):
Camera: side profile, static
Action: Salmon strips, avocado, and cucumber lined up in a row on the nori

Scene 5 — The roll (~2s):
Camera: side profile, static
Action: Bamboo mat presses forward, rolling tightly with even pressure

Scene 6 — The cut (~2s):
Camera: low angle, slow push-in
Action: Knife comes down cleanly, cross-section of roll revealed — hero moment

Scene 7 — The lineup (~2s):
Camera: overhead, slow pull-back
Action: Eight sushi pieces stand upright in a row on hinoki wood board

Scene 8 — The eat (~2s):
Camera: close-up, static
Action: Chef lifts one piece slowly, eyes close softly — quiet satisfaction
```