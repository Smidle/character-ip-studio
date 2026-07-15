---
name: "q-character-generator"
description: "Create a consistent character-IP delivery folder from one uploaded reference image. Use for Q-version/chibi character generation, pixel-art personal IPs, three-view character sheets, or consistent reaction sticker packs. Generate a three-view anchor, eight independent stickers, a character consistency anchor, a verification report, request approval, then organize the approved assets into one folder."
---

# Character IP Generator

Create reusable character-IP assets from one reference image. Use the built-in `image_gen` tool; do not use CLI/API fallback unless the user explicitly asks for it.

## Inputs

Require one uploaded character reference image. Before generating any new character, require a confirmed overall-style brief using the fixed question below. Accept optional:

- Sticker text, output folder name, emotion list, and transparent background.
- An emotion list different from the default eight.

Use no in-image text and a clean light background by default. Preserve the reference character's identity cues: face, hair/headwear, eyes, clothing, accessories, colors, silhouette, and outfit fit.

## Mandatory Overall-Style Brief

For every new character project, ask this exact Chinese multiple-choice question first. Do not generate the three-view sheet or stickers until the user answers or confirms it. If the user has already given some details, preselect them in the same template and ask them to confirm or complete the rest. Translate faithfully only when the user is clearly using another language; preserve the fields, choices, and order.

```text
在开始生成前，请按下面的统一选择题确认整体风格。回复选项编号即可；若选择“其他”，请补充说明。

1. 视觉风格
   A. 3 头身 Q 版 / 软萌角色
   B. 像素风个人 IP
   C. 非 Q 版插画角色
   D. 其他（请说明）

2. 人物比例
   A. 3 头身 Q 版
   B. 成人比例（约 5–7 头身）
   C. 严格沿用参考图比例
   D. 其他（请说明）

3. 画面质感
   A. 软萌赛璐璐 / 干净描边
   B. 粗颗粒像素 / 清晰方格像素
   C. 精细像素 / 有层次的像素阴影
   D. 复古 8-bit / 有限色板
   E. 其他（请说明）

4. 配色
   A. 严格沿用参考图配色
   B. 沿用参考图并强化品牌主色
   C. 自定义配色（请说明）

5. 背景
   A. 浅色纯色背景
   B. 透明背景
   C. 其他（请说明）

6. 识别元素
   A. 保留参考图全部识别元素
   B. 保留关键元素（请列出，例如帽子、眼镜、服装）
   C. 其他（请说明）

7. 贴纸使用场景
   A. 聊天表情
   B. 社媒配图
   C. 品牌素材
   D. 其他（请说明）

示例回复：1B，2C，3B，4A，5A，6A，7C。

确认后，我会按“整体风格 → 三视图 → 8 张表情 → 一致性检查 → 你确认后交付”的流程制作。
```

Treat the approved answer as the **overall-style brief**. Repeat its constraints in the three-view prompt, character anchor, every sticker prompt, and the verification report. Do not silently substitute defaults for unanswered fields; ask one concise follow-up only for the missing detail that would materially change the output.

## Style Selection

Follow the confirmed overall-style brief. An explicit request for pixel art or non-Q proportions overrides the Q-version default.

### Q-version mode (default)

- Use balanced 3-heads-tall proportions, with the head about one third of total height.
- Use polished 2D anime mascot/chibi rendering, clean outlines, and soft cel shading.
- Avoid a giant head, a compressed torso, realism, 3D, and photorealism.

### Pixel-art mode

Trigger on requests such as “像素风”, “pixel art”, “个人 IP”, “非 Q 版”, or an uploaded pixel-art reference.

- Use the reference's intended age and balanced, non-chibi body proportions. For an adult IP, target roughly 5–7 heads tall unless the user asks otherwise.
- Use deliberately visible square pixels, crisp stepped outlines, a limited palette, and clustered pixel shading.
- Preserve the reference's existing pixel technique if it is already pixel art.
- Avoid Q/chibi proportions, oversized heads, smooth gradients, blur, anti-aliasing, vector art, 3D, anime rendering, and photorealism.

## Output Structure

Create `output/q-character-generator-<short-slug>/` with:

```text
00-three-view.png
01-happy-wave.png
02-thumbs-up.png
03-thinking.png
04-shocked.png
05-working-hard.png
06-crying.png
07-angry-cute.png
08-salute-received.png
character-anchor.md
consistency-check.md
```

Do not create a zip unless explicitly requested. Finalize this folder only after explicit user approval.

## Workflow

1. Ask the mandatory overall-style brief and wait for the user's confirmation.
2. Inspect the reference and confirmed brief; identify stable identity, outfit, silhouette, palette, and style traits.
3. Select the style mode from the confirmed brief.
4. Generate a front, strict side, and back full-body three-view sheet; save it as `00-three-view.png`.
5. Regenerate once if the views are inconsistent or violate the confirmed brief.
6. Write `character-anchor.md` from the reference, confirmed brief, and selected sheet.
7. Generate eight independent stickers, one image per file, using the original reference, `00-three-view.png`, and anchor as strict references.
8. Check every sticker against the anchor and confirmed brief; regenerate only failed stickers.
9. Write `consistency-check.md`, show the folder, and ask for approval.
10. After approval, mark the report finalized and deliver the same folder.

## Three-view Prompt

Use this template, replacing the bracketed style block with the selected mode.

```text
Use case: stylized-concept
Asset type: reusable character IP three-view turnaround
Primary request: Based on the uploaded reference, create a clean three-view character design sheet.
Input images: Uploaded image is the strict identity, outfit, body silhouette, and color reference.
Subject: one version of the referenced character, with front view, strict side view, and back view.
Overall-style brief: <paste the user's approved seven-item response verbatim or as a faithful concise summary>.
Style block: <Q-version mode: balanced 3-heads-tall polished 2D chibi mascot, head about one third of height, clean outline and soft cel shading. OR Pixel-art mode: adult/non-chibi proportions matching the reference, visible square pixels, crisp stepped outlines, limited palette, clustered pixel shading.>
Composition/framing: three equal-scale full-body figures side by side, aligned feet, generous spacing, all bodies fully visible.
Scene/backdrop: clean warm off-white or light neutral background.
Constraints: no text labels, watermark, logos, extra characters, or unrelated props. Keep identity, outfit, headwear/hairstyle, accessories, colors, and proportions consistent across views. <Q-version: no giant head, realism, 3D, or photorealism. Pixel-art: no Q/chibi anatomy, oversized head, anti-aliasing, blur, gradients, vectors, 3D, anime, or photorealism.>
```

## Character Anchor

Write `character-anchor.md` with concrete observations, not placeholders:

```markdown
# Character Consistency Anchor

## Source

- Original reference image: user-uploaded image.
- Three-view anchor image: `00-three-view.png`.

## Approved Overall-Style Brief

- <Record the user's confirmed seven-item response.>

## Identity

- <age/category and general character type>
- <face shape, skin tone, eyes, hair/headwear, baseline expression>

## Outfit

- <top, bottom, shoes, accessories, and important colors>

## Drawing Style

- <Q-version mode details OR pixel-art mode details>

## Hard Consistency Rules

- Keep the same identity, outfit, hairstyle/headwear, accessories, colors, body silhouette, and outfit fit.
- Follow the selected style and proportions from `00-three-view.png`.
- <Q-version: head about one third of total height; no giant-head mascot proportions.>
- <Pixel-art: preserve visible square pixels, crisp stepped outlines, limited palette, clustered shading, and non-chibi proportions; no anti-aliasing or smooth rendering.>
- Do not add unrelated props, text, logos, watermarks, or extra characters unless explicitly requested.
```

## Sticker Generation

Generate one independent image for each default sticker:

1. Happy wave — cheerful smile, one hand raised and waving.
2. Thumbs up — confident gentle smile, one clear thumbs-up.
3. Thinking — hand touching chin, eyes/head angled slightly upward.
4. Shocked — wide eyes, small open mouth, hands near cheeks.
5. Working hard — focused face, one fist near chest; small sweat drop allowed.
6. Crying — watery eyes, tears, hands near chest.
7. Angry but cute — pout, slightly puffed cheeks, lowered brows, arms crossed.
8. Salute / received — attentive smile, one hand at cap brim or temple.

Use this base prompt, changing only pose/expression:

```text
Use case: stylized-concept
Asset type: independent character IP reaction sticker
Primary request: Generate sticker <N> of 8: <emotion/action>, using `00-three-view.png` and `character-anchor.md` as strict consistency references.
Input images: The uploaded original image and `00-three-view.png` are identity references.
Subject: the same character described in `character-anchor.md`.
Pose/expression: <specific pose>.
Overall-style brief: <use the confirmed brief recorded in `character-anchor.md`>.
Style/medium: <selected Q-version or pixel-art mode from the anchor>.
Composition/framing: single centered character with generous padding on a clean light background; show full body when it helps preserve the chosen proportions.
Constraints: preserve all identity, outfit, palette, and style rules from the anchor. No text, watermark, logo, extra characters, unrelated props, or scene background. <Pixel-art: no Q proportions, anti-aliasing, blur, gradients, vector, 3D, anime, or photorealism.>
```

## Verification and Approval

Create `consistency-check.md` with a Pass/Fail row for each sticker and check:

- Same character identity, headwear/hairstyle, outfit, accessories, and palette.
- Same selected proportions and recognizable silhouette.
- Same selected drawing style.
- Same approved overall-style brief.
- No unwanted text, watermark, logo, extra character, or unrelated prop.

If a hard rule fails, regenerate only that sticker with a targeted prompt. Before finalizing, show the output folder and ask the user to approve the three-view sheet and all eight stickers. After approval, change the delivery status to finalized and report the folder path.

## Transparent Backgrounds

For transparent sticker requests, follow the `imagegen` skill's built-in chroma-key workflow, remove the background locally, and validate alpha before final delivery. Do not switch to native CLI transparency without explicit user confirmation.
