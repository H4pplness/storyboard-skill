---
name: storyboard-poster
description: "Xây dựng bộ prompt cho storyboard video ngắn. Dùng khi người dùng muốn storyboard cho video ẩm thực, nhân vật, sản phẩm, quy trình, hoặc bất kỳ nội dung ngắn nào cần trực quan hóa theo từng cảnh. Đầu ra mặc định: một prompt poster storyboard và một video prompt cho các app AI tạo video (Seedance, Kling, Runway, Pika). Nếu người dùng yêu cầu character reference sheet, thêm prompt đó vào trước. Kích hoạt khi: storyboard, shot breakdown, scene planning, video prompt, short video, reel planning, shooting script, shot list, visualize a video concept."
---

# Storyboard Poster Skill

Tạo ra tối đa ba khối prompt mà người dùng có thể dán vào các AI tạo ảnh / video:

1. **Character Reference Sheet** — chỉ khi người dùng yêu cầu
2. **Storyboard Poster** — luôn tạo (infographic 16:9, nhiều panel)
3. **Video Prompt** — luôn tạo (Seedance / Kling / Runway / Pika)

Hành vi mặc định: tạo khối 2 và 3. Chỉ thêm khối 1 khi người dùng yêu cầu rõ ràng.

---

## Khối 1 — Prompt Character Reference Sheet *(chỉ khi được yêu cầu)*

Một ảnh ngang duy nhất chứa: tư thế hero · góc xoay front/side/back · 2 crop chi tiết (mặt + trang phục) · bảng biểu cảm (4+ chân dung bust) · dải footer (bảng màu + chất liệu + tagline). Cùng phong cách render với storyboard.

Template:

```
Tạo một character reference sheet chuyên nghiệp dưới dạng một poster thống nhất.
Định dạng: ngang, [NỀN], viền đen mỏng giữa các vùng, nhãn sans-serif in đậm.
MỘT ảnh duy nhất — không tách thành nhiều ảnh riêng.

STYLE: [RENDER_STYLE — ví dụ: Pixar 3D stylized / hyper-realistic / anime cel-shaded /
flat vector / Ghibli hand-painted]
Ánh sáng: [studio soft-box / overhead spot / natural window]

NHÂN VẬT:
• Tên: [tên]
• Tuổi & dáng: [tuổi, giới tính, dáng người]
• Tông da: [mô tả cụ thể]
• Tóc: [màu, độ dài, kiểu]
• Mắt: [màu + đặc điểm]
• Đặc điểm nhận dạng: [một đặc trưng nổi bật]
• Trang phục: [từ trên xuống dưới kèm chất liệu và màu sắc]
• Bảng màu: [4–6 màu, nên dùng mã hex]

CÁC VÙNG:
• Hero pose: toàn thân góc 3/4 (30°), tư thế phù hợp với concept video
• Góc xoay: front (0°) / side (90°) / back (180°), A-pose trung tính, cùng tỷ lệ,
  đường guideline tại đỉnh đầu/vai/hông/gót chân
• Crop chi tiết: (1) mặt — đặc điểm nhận dạng + texture da; (2) trang phục — vải + phụ kiện chính
• Bảng biểu cảm: [N≥4] chân dung bust, góc 3/4, ánh sáng giống hệt,
  gán nhãn cảm xúc phù hợp với mạch video
• Dải footer: swatch màu · ghi chú chất liệu · tagline một dòng
```

Sau khi tạo xong, người dùng upload sheet này làm ảnh tham chiếu cho lần gen storyboard.

---

## Khối 2 — Prompt Storyboard Poster

Template:

```
Tạo một poster storyboard infographic sắc nét.
Bố cục: rộng 16:9, nền trắng, viền đen, chữ in đậm đen.
Phong cách render: [RENDER_STYLE — phải khớp với reference sheet nếu có]

[NẾU có reference sheet, thêm vào:]
NHẤT QUÁN NHÂN VẬT: Tất cả panel có [tên] phải khớp chính xác với reference sheet
đính kèm — cùng tóc, da, trang phục, đặc điểm nhận dạng. Dùng hero pose làm neo.

HEADER:
• Tiêu đề IN HOA
• TỔNG THỜI LƯỢNG VIDEO: [Y] GIÂY
• [N] CẢNH · [từ khóa mood 1] · [từ khóa mood 2] · [từ khóa mood 3]
• Hàng legend: [4 nhãn icon ngắn phù hợp với video — xem hướng dẫn legend bên dưới]

COMMON BRIEF:
• Nhân vật: [một câu — hoặc "xem reference sheet đính kèm"]
• Bối cảnh: [địa điểm, đạo cụ, ánh sáng]
• Bảng màu: [4–7 màu, phải khớp reference sheet]
• Tông: [2–3 từ khóa]
• Mạch: [một câu từ X → Y]

PANELS:
Shot [N] — [tên cảnh]:
[Hành động chính]. [Chi tiết màu/texture]. [Trạng thái nhân vật nếu có]. [Vai trò trong mạch] [GÓC MÁY]
...
Đánh dấu cảnh cao trào bằng ★.

FOOTER:
• VIDEO FLOW: [N] cảnh × ~[X]s = [Y]s. [Một câu tóm tắt mạch]
• CAMERA TIPS: [các góc đã dùng và khi nào]
• LIGHT & STYLE: [bảng màu + tóm tắt ánh sáng]
• DIRECTOR NOTES: [một câu sáng tạo]
```

### Ký hiệu góc máy

| Ký hiệu | Ý nghĩa |
|---|---|
| `[OVH]` | Overhead — nhìn thẳng từ trên xuống |
| `[LOW]` | Low angle — nhìn từ dưới lên |
| `[SIDE]` | Side profile — nhìn ngang |
| `[CLOSE]` | Tight close-up — cận cảnh |
| `[POV]` | First-person view — góc nhìn thứ nhất |

### Hướng dẫn hàng legend

Chọn 4 nhãn ngắn phù hợp với loại video:
- **Ẩm thực/nấu ăn**: `ACTION · HEAT · TIME · INGREDIENT`
- **Nhân vật**: `ACTION · EMOTION · LOCATION · MOMENT`
- **Sản phẩm**: `FEATURE · ANGLE · CONTEXT · DETAIL`
- **Quy trình**: `INPUT · STEP · TOOL · OUTPUT`

---

## Khối 3 — Video Prompt (Seedance / Kling / Runway / Pika)

Template:

```
VIDEO PROMPT — [TIÊU ĐỀ]

GHI CHÚ NHÂN VẬT: [tên] — [một câu: tóc + trang phục chính + đặc điểm nhận dạng]
[Bỏ dòng này nếu không có nhân vật]

STYLE & SETTING:
[1–2 câu: bối cảnh, phong cách render, tông màu, ánh sáng]

SCENES:

Scene [N] — [tên cảnh] (~[X]s):
Camera: [góc + chuyển động, ví dụ: "low angle, slow push-in"]
Nhân vật: [trạng thái/biểu cảm — bỏ dòng này nếu không có nhân vật trong cảnh]
Action: [một câu, động từ hành động mạnh]
...
```

Quy tắc: camera phải có cả góc VÀ chuyển động. Action dùng động từ cụ thể (cắt, nâng, xoay), không bao giờ mô tả ngoại hình. Tổng thời lượng các scene phải bằng tổng thời gian storyboard.

---

## Biến thể nhanh

| Loại video | Reference sheet? | Gợi ý phong cách render | Mạch mẫu |
|---|---|---|---|
| Nhân vật / narrative | Theo yêu cầu | phù hợp cá tính | thiết lập → hành động đặc trưng → reveal |
| Ẩm thực / nấu ăn | Theo yêu cầu (chỉ nếu mặt đầu bếp xuất hiện) | Pixar 3D hoặc hyper-realistic | nguyên liệu → thành phẩm → cắn miếng đầu |
| Sản phẩm | Bỏ qua | clean studio product photography | unbox → tính năng → sử dụng → beauty |
| Quy trình | Bỏ qua | flat vector infographic | vấn đề → các bước → kết quả |

---

## Checklist tổng

- [ ] Số shot trong header khớp với số panel thực tế
- [ ] Cảnh cao trào được đánh dấu ★
- [ ] Mỗi shot có: hành động + môi trường + trạng thái nhân vật (nếu có) + góc máy
- [ ] Bảng màu nhất quán giữa reference sheet (nếu dùng), panel storyboard, và video prompt
- [ ] Nếu dùng reference sheet, khối `NHẤT QUÁN NHÂN VẬT` có trong prompt storyboard
- [ ] Video prompt: mỗi scene có Camera + Action (+ Nhân vật nếu có) + thời lượng
- [ ] Tổng thời lượng các scene bằng tổng thời gian video

---

## Ví dụ — The Sushi Chef (storyboard + video prompt)

### Prompt Storyboard Poster

```
Tạo một poster storyboard infographic sắc nét.
Bố cục: rộng 16:9, nền trắng, viền đen, chữ in đậm đen.
Phong cách render: premium Pixar 3D stylized.

HEADER:
• THE SUSHI CHEF
• TỔNG THỜI LƯỢNG VIDEO: 12 GIÂY
• 8 CẢNH · SHARP · PRECISE · HYPNOTIC
• Hàng legend: ACTION · HEAT · TIME · INGREDIENT

COMMON BRIEF:
• Nhân vật: nam đầu bếp trẻ người Nhật, áo khoang trắng double-breasted, tạp dề than,
  băng đô trắng, tóc đen ngắn, tập trung điềm tĩnh
• Bối cảnh: quầy gỗ hinoki, mành tre, ánh sáng overhead spot ấm
• Bảng màu: coral salmon · ivory rice · jade avocado · jet-black nori ·
  hinoki wood · soft ivory steam
• Tông: sắc nét · thiền định · thỏa mãn sâu
• Mạch: từ gạo sống đến miếng cắn đầu tiên — một cuộn, tám miếng hoàn hảo

PANELS:
Shot 1 — Gập cơm: Đôi tay gập cơm nóng bằng mái chèo tre. Ivory ấm. Mở đầu tĩnh. [OVH]
Shot 2 — Nori soi sáng: Miếng nori giơ lên ánh sáng, đen tuyền và trong mờ. Đồ họa. [SIDE]
Shot 3 — Trải cơm: Mái chèo kéo cơm trắng trên nori đen. Tương phản trắng-đen. [OVH]
Shot 4 — Xếp nhân: Cá hồi, bơ, dưa leo xếp hàng. Panel nhiều màu nhất. [SIDE]
Shot 5 — Cuộn: Mành tre ép về trước, lực đều. Nén. [SIDE]
Shot 6 — Cắt ★: Dao hạ xuống, mặt cắt lộ ra — coral, jade, trắng, đen. Hero. [LOW]
Shot 7 — Đội hình: Tám miếng đứng thẳng trên thớt hinoki. Beauty shot. [OVH]
Shot 8 — Nếm: Đầu bếp nhấc một miếng, mắt nhắm lại. Hơi nước bốc lên. Grace note. [CLOSE]

FOOTER:
• VIDEO FLOW: 8 cảnh × ~1.5s = 12 giây. Từ gạo đến cuộn đến tĩnh lặng.
• CAMERA TIPS: overhead cho chuẩn bị + đội hình, low cho cú cắt, side cho cuộn, close cho nếm.
• LIGHT & STYLE: overhead spot ấm, coral salmon, jade, trắng, đen tuyền, hinoki.
• DIRECTOR NOTES: một đầu bếp, một cuộn, tám miếng hoàn hảo.
```

### Video Prompt

```
VIDEO PROMPT — THE SUSHI CHEF

GHI CHÚ NHÂN VẬT: Nam đầu bếp Nhật — tóc đen ngắn, áo khoang trắng tinh
với tạp dề than, băng đô trắng ngang trán.

STYLE & SETTING:
Pixar 3D stylized. Quầy omakase sạch sẽ với ánh sáng overhead spot ấm.
Tông ivory và coral, không khí thiền định.

SCENES:

Scene 1 — Gập cơm (~1.5s):
Camera: overhead, static
Action: Mái chèo tre gập cơm nóng trong bát gỗ

Scene 2 — Nori soi sáng (~1.5s):
Camera: side profile, static
Nhân vật: tập trung, mắt khóa vào nori
Action: Đầu bếp giơ nori lên ánh sáng, trong mờ dưới đèn spot

Scene 3 — Trải cơm (~1.5s):
Camera: overhead, slow push-in
Action: Mái chèo kéo cơm ngang nori đen trong một chuyển động mượt

Scene 4 — Xếp nhân (~1.5s):
Camera: side profile, static
Action: Đầu bếp đặt cá hồi, bơ, dưa leo thành hàng chính xác trên nori

Scene 5 — Cuộn (~1.5s):
Camera: side profile, static
Action: Mành tre ép về trước, cuộn chặt với lực đều

Scene 6 — Cắt (~1.5s):
Camera: low angle, slow push-in
Nhân vật: tập trung cao độ
Action: Dao hạ xuống sạch sẽ, mặt cắt cuộn lộ ra

Scene 7 — Đội hình (~1.5s):
Camera: overhead, slow pull-back
Action: Tám miếng sushi đứng thẳng hàng trên thớt hinoki

Scene 8 — Nếm (~1.5s):
Camera: close-up, static
Nhân vật: hài lòng tĩnh lặng, mắt nhắm nhẹ
Action: Đầu bếp từ từ nhấc một miếng lên môi, hơi nước bốc lên
```
