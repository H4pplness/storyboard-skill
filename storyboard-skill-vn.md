---
name: storyboard-poster
description: >
  Tạo prompt hoàn chỉnh để gen một infographic storyboard poster cho video ngắn (dưới 60 giây).
  Dùng khi người dùng muốn: storyboard cho video ẩm thực, sản phẩm, nhân vật, quy trình, hoặc
  bất kỳ nội dung ngắn nào cần visualize cảnh-theo-cảnh — mô tả nhân vật trực tiếp bằng văn bản,
  không cần character prototype có sẵn.
  Sau khi tạo storyboard, tự động gen thêm video prompt ngắn gọn cho các app gen video như
  Seedance, Kling, Runway, Pika — gồm style/setting tổng thể và mô tả camera + action từng scene.
  Output là: (1) storyboard prompt cho image-gen AI, và (2) video prompt cho video-gen AI.
  Nếu người dùng đã có character prototype / concept sheet, dùng skill character-prototype thay thế.
---
 
# Storyboard Poster Skill
 
Skill này giúp bạn xây dựng prompt để gen ra một tờ poster storyboard dạng infographic —
bố cục 16:9, nhiều panel, có header/footer mô tả kỹ thuật quay.
 
Nhân vật được mô tả hoàn toàn bằng văn bản trong Common Brief.
Nếu người dùng đã có prototype nhân vật, hãy dùng skill **character-prototype** thay thế.
 
---
 
## Cấu trúc prompt — 3 lớp
 
```
[LAYER 1 — AI Instructions]
[LAYER 2 — Common Brief]
[LAYER 3 — Panel Descriptions]
```
 
---
 
## Lớp 1 — AI Instructions
 
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
 
> **`[RENDER_STYLE]`** — thay bằng phong cách render:
> `premium Pixar 3D stylized` · `flat vector illustration` · `hyper-realistic` ·
> `anime cel-shaded` · `minimal line art, monochrome`
 
---
 
## Lớp 2 — Common Brief
 
```
COMMON BRIEF:
• Character: [giới tính, độ tuổi, ngoại hình, trang phục, biểu cảm chủ đạo]
• Setting: [địa điểm, đạo cụ cố định, kiểu ánh sáng]
• Color palette: [4–7 màu/vật liệu chủ đạo]
• Tone & feel: [2–3 từ cảm xúc]
• Total duration: [N shots × ~Xs = Y seconds]
• Arc summary: [1 câu hành trình cảm xúc: từ X → đến Y]
```
 
---
 
## Lớp 3 — Panel Descriptions
 
```
Shot [N] — [TÊN CẢNH]:
[Hành động chính]. [Chi tiết màu/texture]. [Vai trò trong arc] [GÓC MÁY]
```
 
**Ký hiệu góc máy:**
 
| Ký hiệu | Nghĩa |
|---|---|
| `[OVH]` | Overhead locked — nhìn thẳng từ trên xuống |
| `[LOW]` | Dramatic low angle — nhìn từ dưới lên |
| `[SIDE]` | Side profile — nhìn ngang |
| `[CLOSE]` | Tight close-up — macro, chi tiết |
| `[POV]` | Point of view — góc nhìn nhân vật |
 
---
 
## Checklist trước khi gửi prompt
 
- [ ] Số shot trong header khớp với số panel thực tế
- [ ] Có ít nhất 1 shot đánh dấu "hero frame" / đỉnh điểm
- [ ] Arc summary phản ánh đúng hành trình Shot 1 → Shot N
- [ ] Mỗi shot có: hành động + chi tiết môi trường + vai trò arc + góc máy
- [ ] Common Brief có đủ: character · setting · color palette · tone · duration
- [ ] Màu trong Common Brief khớp với màu mô tả trong các panel
---
 
## Bước bổ sung — Gen Video Prompt (Seedance / Kling / Runway / Pika)
 
Sau khi đã tạo xong storyboard prompt, **tự động gen thêm một video prompt** dành cho các ứng dụng gen video AI.
 
> Mục tiêu: prompt ngắn gọn, rõ ràng — đủ để AI video hiểu bối cảnh, style, và hành động từng scene.
> Tập trung vào: **setting · visual style · camera · action**.
 
### Cấu trúc Video Prompt
 
```
VIDEO PROMPT — [TÊN VIDEO]
 
STYLE & SETTING:
[1–2 câu mô tả tổng thể: bối cảnh, render style, tông màu, ánh sáng chủ đạo]
 
SCENES:
 
Scene [N] — [TÊN CẢNH] (~[X]s):
Camera: [góc máy + movement]
Action: [mô tả hành động chính xảy ra trong scene]
 
[Lặp lại cho các scene còn lại]
```
 
### Hướng dẫn viết từng phần
 
**STYLE & SETTING** (1–2 câu):
- Bối cảnh là gì, ở đâu, thời điểm nào
- Visual style: `Pixar 3D` · `cinematic live-action` · `anime` · `flat 2D` · `hyper-realistic`
- Tông màu và ánh sáng nổi bật
**Camera** (ngắn gọn):
- Góc: `overhead` · `low angle` · `side profile` · `close-up` · `POV`
- Movement: `static` · `slow push-in` · `tracking` · `pan left/right` · `tilt up/down`
**Action** (1 câu, động từ mạnh):
- Mô tả **hành động chính** xảy ra trong scene
- Ưu tiên động từ cụ thể: `slices` · `walks forward` · `lifts` · `turns to face camera`
### Checklist Video Prompt
 
- [ ] STYLE & SETTING đủ ngắn — tối đa 2 câu
- [ ] Mỗi scene có đủ 3 phần: Camera · Action · Thời lượng gợi ý
- [ ] Camera có cả góc + movement
- [ ] Action dùng động từ cụ thể, mô tả **hành động** không mô tả ngoại hình
- [ ] Tổng thời lượng các scene khớp với storyboard
---
 
## Biến thể theo loại video
 
### Video ẩm thực (cooking / food prep)
- Render style: `Pixar 3D` hoặc `hyper-realistic`
- Arc: nguyên liệu thô → thành phẩm → khoảnh khắc thưởng thức
- Hero frame: cắt lát / plating / cắn miếng đầu tiên
### Video nhân vật / character showcase
- Render style: chọn theo cá tính nhân vật
- Arc: thiết lập bối cảnh → hành động đặc trưng → reveal cảm xúc
- Hero frame: close-up biểu cảm hoặc action signature move
- Lưu ý: nếu cần giữ nhất quán cao với nhân vật đã có, dùng skill **character-prototype**
### Video sản phẩm (product showcase)
- Render style: `clean studio product photography, white cyclorama`
- Character: có thể bỏ hoặc dùng hands-only
- Arc: unboxing → features → in-use → beauty shot
### Video quy trình / how-it-works
- Render style: `flat vector, bold outlines, infographic style`
- Không cần character cố định
- Arc: vấn đề → các bước → kết quả
---
 
## Ví dụ prompt hoàn chỉnh — The Sushi Chef
 
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
 
## Ví dụ Video Prompt — The Sushi Chef
 
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
 