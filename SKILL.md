---
name: "character-ip-studio"
description: "Build a reusable character-IP asset kit from a reference image. Use when someone needs a stylized character, pixel-art avatar, illustrated personal IP, turnaround sheet, or a coordinated reaction set. Start with a visual-direction questionnaire, create a model sheet and eight pose assets, audit the set, and finalize only after approval."
---

# Character IP Studio

Turn one reference image into a coherent set of reusable character assets. Use the built-in image generation tool for artwork. Keep every generated asset in the workspace and never overwrite an existing delivery without permission.

## Start with a creative selection

For each new character, ask the following Chinese multiple-choice form before creating artwork. If the request already answers some items, mark those choices and ask for confirmation of the rest. Wait for the reply before moving on.

```text
先确定这套角色素材的创意方向。请回复每题的选项编号；选择“其他”时补充说明。

1. 画风
   A. 轻松可爱的卡通风
   B. 像素艺术
   C. 现代插画
   D. 其他（请说明）

2. 身材设定
   A. 迷你卡通比例
   B. 写实偏简化的成人比例
   C. 以参考图身材为准
   D. 其他（请说明）

3. 画面细节
   A. 简洁色块与清楚线条
   B. 明显的方格像素与块状明暗
   C. 细腻像素与丰富层次
   D. 复古低分彩色风格
   E. 其他（请说明）

4. 色彩策略
   A. 原样保留参考图的色彩
   B. 以参考图为基础强化主色
   C. 自定义（请说明）

5. 画布底色
   A. 明亮纯色
   B. 透明
   C. 其他（请说明）

6. 角色记忆点
   A. 完整保留参考图的外观特征
   B. 仅保留指定特征（请列出）
   C. 其他（请说明）

7. 使用目的
   A. 聊天贴纸
   B. 社交媒体内容
   C. 品牌视觉资产
   D. 其他（请说明）

示例：1B，2C，3B，4A，5A，6A，7C。
```

Treat the confirmed choices as the **creative direction**. Carry them through the whole job. Ask a short follow-up only when an unanswered item would alter the result.

## Establish the character

Review the reference image for its silhouette, face, hair or headwear, clothing, accessories, palette, and mood. Then create a single image with three matched full-body views: facing forward, true profile, and rear. Keep their scale and clothing aligned.

Use this design brief, replacing bracketed text with the confirmed direction:

```text
Create a reusable character model sheet based on the supplied reference image.
The reference establishes the person or character, key appearance cues, outfit, and core palette.
Show three full-body views at the same scale: front, strict side, and back. Keep feet aligned and leave clean space between views.
Creative direction: <summarize the confirmed choices>.
Visual rules: <apply the chosen style, body setting, detail level, color plan, and background>.
Protect the character's recognizable features across all three views. Do not add text, logos, watermarks, unrelated objects, or additional characters.
```

If the views disagree on identity, clothing, or the confirmed direction, correct the model sheet once before producing poses.

## Build the pose collection

Create eight separate assets from the approved model sheet. Preserve the face, outfit, proportions, palette, and rendering method. Use these default moments unless the user supplies replacements:

1. Friendly greeting — open hand wave.
2. Positive signal — clear thumbs-up.
3. Considering — hand near chin, reflective stance.
4. Surprise — raised hands and startled expression.
5. In focus — determined stance with a clenched fist.
6. Upset — visible tears and hands close to the chest.
7. Firm but playful — frown with crossed arms.
8. Acknowledged — relaxed salute or cap-brim gesture.

For each pose, use the original reference and model sheet as visual sources. Keep the character isolated on the agreed canvas treatment. Do not make a contact sheet.

## Deliverable layout

Create `deliverables/character-ip-<short-name>/` and save:

```text
model-sheet.png
pose-greeting.png
pose-positive.png
pose-considering.png
pose-surprise.png
pose-focus.png
pose-upset.png
pose-firm.png
pose-acknowledged.png
identity-notes.md
quality-review.md
```

Write `identity-notes.md` with the confirmed creative direction and concrete observations about the identity, clothing, color plan, body setting, and rendering treatment. Write `quality-review.md` with a Pass/Needs-work entry for every pose, checking:

- Identity and distinctive features remain recognizable.
- Clothing, accessories, proportions, and palette agree with the model sheet.
- The chosen art treatment and background are followed.
- No unwanted lettering, watermark, unrelated prop, or extra character appears.

Regenerate only the asset that fails review. Show the completed folder for approval. After the user approves it, record that the folder is final. Do not create an archive unless explicitly requested.

## Transparent canvases

When transparency is selected, use the built-in image workflow with a flat chroma-key background, remove it locally, and inspect the alpha result before approval. Do not switch to a command-line image workflow without explicit permission.
