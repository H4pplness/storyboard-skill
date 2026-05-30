# Storyboard Skill

Bộ kỹ năng AI dùng để tạo poster storyboard dạng infographic và video prompt cho nội dung video ngắn (dưới 60 giây).

## Có gì trong repo này

Repo chứa hai kỹ năng dành cho hai nền tảng AI khác nhau:

### 1. Storyboard Poster Skill — Claude

Một custom skill cho Claude Code, giúp xây dựng bộ prompt hoàn chỉnh cho các AI tạo ảnh và tạo video.

**Đầu ra bao gồm:**

| Khối | Mô tả | Khi nào |
|---|---|---|
| Character Reference Sheet | Một poster ngang với hero pose, góc xoay (front/side/back), crop chi tiết, bảng biểu cảm, và footer | Khi người dùng yêu cầu |
| Storyboard Poster Prompt | Prompt infographic 16:9 hoàn chỉnh với từng panel cảnh, ghi chú quay phim, header/footer | Luôn luôn |
| Video Prompt | Prompt ngắn gọn cho các app tạo video AI (Seedance, Kling, Runway, Pika) kèm mô tả camera và hành động từng cảnh | Luôn luôn |

**Loại video hỗ trợ:** Ẩm thực/Nấu ăn · Giới thiệu nhân vật · Giới thiệu sản phẩm · Quy trình/Hướng dẫn

**Phiên bản ngôn ngữ:**
- [Tiếng Anh](storyboard-skill-en.md)
- [Tiếng Việt](storyboard-skill-vn.md)

### 2. Storyboard ChatGPT Executor Skill — ChatGPT

Một system prompt cho ChatGPT, chỉ cần copy-paste là dùng được. ChatGPT sẽ phỏng vấn nhanh người dùng, sau đó **trực tiếp tạo ảnh** bằng DALL·E — không cần copy-paste prompt qua lại.

**Đầu ra bên trong ChatGPT:**
1. **Ảnh Character Reference Sheet** — một poster tổng hợp với hero pose, góc xoay, crop chi tiết, bảng biểu cảm
2. **Ảnh Storyboard Poster** — infographic 16:9 với lưới panel, header, footer, và ghi chú góc máy
3. **Video Prompt dạng text** (tùy chọn) — dành cho Kling, Runway, Seedance, hoặc Pika

**Phiên bản ngôn ngữ:**
- [Tiếng Anh](storyboard-chacracter-ref-chatgpt-en.md)
- [Tiếng Việt](storyboard-chacracter-ref-chatgpt-vn.md)

**Cách dùng:** Copy toàn bộ nội dung từ file skill và dán vào ChatGPT (vào system prompt nếu dùng Plus/Custom GPT, hoặc tin nhắn đầu tiên nếu dùng bản miễn phí).

## Ví dụ đầu ra

### Poster storyboard

![Storyboard poster example](output-storyboard.png)

### Video đã tạo

<video src="output-video.mp4" controls width="100%"></video>

> Kết quả sau khi dán prompt được sinh ra vào AI tạo ảnh và AI tạo video.

## Cách dùng

### ChatGPT skill

1. Trong ChatGPT, tạo một **Project mới**
2. Dán toàn bộ nội dung từ [storyboard-chacracter-ref-chatgpt-en.md](storyboard-chacracter-ref-chatgpt-en.md) (hoặc [bản tiếng Việt](storyboard-chacracter-ref-chatgpt-vn.md)) vào trường **system prompt / Instructions** của project
3. Bắt đầu chat mới trong project và mô tả ý tưởng video của bạn
4. ChatGPT sẽ phỏng vấn nhanh vài câu, rồi trực tiếp tạo ảnh Character Reference Sheet và Storyboard Poster qua DALL·E — không cần copy-paste prompt qua lại

### Claude Code skill

1. Mở Claude Code và đưa file skill cho nó: "Dùng [storyboard-skill-en.md](storyboard-skill-en.md) (hoặc [bản tiếng Việt](storyboard-skill-vn.md)) để tạo một skill"
2. Claude Code sẽ đăng ký nó thành custom skill
3. Kích hoạt skill bằng cách nhắc đến: storyboard, shot breakdown, scene planning, video prompt, short video, reel planning, shooting script, shot list, hoặc yêu cầu hình dung ý tưởng video theo từng cảnh
4. Claude sẽ xuất ra prompt văn bản để bạn dán vào AI tạo ảnh (Midjourney, DALL·E, v.v.) và AI tạo video (Seedance, Kling, Runway, Pika)
