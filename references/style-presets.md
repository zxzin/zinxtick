# Style Presets

Use this file to keep style selection simple. Do not ask ordinary users to invent art direction language. Offer the menu, recommend preset 1 when they are unsure, and only collect custom wording when they choose preset 6.

## Style Selection Menu

Ask this exact short question when the user has not specified style:

```text
选一个风格：1 大众通用美术  2 漫画风格  3 经典贴纸风格  4 强烈平面设计风格  5 古早QQ聊天风格  6 自定义。默认推荐 1。
```

Rules:

- If the user says `默认`, `随便`, `大众`, `通用`, or does not care, use preset 1.
- If the user picks 6, ask for one short style description or reference image.
- If the custom description is vague, combine it with preset 1's quality bar.
- Do not mix multiple presets unless the user explicitly asks.
- Keep the selected style consistent across every sticker in the pack.
- For style comparison demos, generate each style as a separate image first, then compose a board from the real images. Do not rely on one image-generation prompt to render all styles in a single sheet when the goal is to show strong differences.

## Style Depth Rules

Style must change the visual language, not only surface decoration. When using or comparing style presets, specify at least these dimensions:

```text
linework:
shape_language:
color_system:
lighting_rendering:
background_space:
motion_symbols:
texture_finish:
caption_treatment:
hard_negatives:
```

For each selected style, make the differences visible at thumbnail size:

- Preset 1 should feel like polished mainstream cartoon merchandise.
- Preset 2 should feel like a comic panel with bolder line rhythm, impact marks, and stronger emotion.
- Preset 3 should feel like a clean cutout sticker, with thick white border and minimal scene.
- Preset 4 should feel graphic and designed, with strong geometry, limited palette, and poster-like composition.
- Preset 5 should feel like nostalgic early chat emoticon UI, with glossy icon lighting and blue-white digital nostalgia.
- Preset 6 should follow the custom reference, but still stay sticker-readable.

Reject style comparisons where the same drawing appears with only a background/color/filter change. If the silhouette, linework, color system, rendering, and composition do not meaningfully change, regenerate the weak styles separately.

## Preset 1: 大众通用美术

Use for the broadest audience and as the default recommendation.

```text
大众通用表情包美术：圆润可爱但不低幼，干净高级的现代卡通，主体轮廓清晰，柔和粗描边，饱满块面，轻微立体光影，颜色明快但不过饱和，动作夸张但不怪异，白色贴纸外轮廓或干净透明背景，64px缩略图也能看懂，适合微信/LINE/Telegram聊天发送。
避免：写实照片、油腻AI质感、复杂背景、廉价儿童泡泡字、暗黑恐怖、赛博朋克、过度二次元、凌乱小装饰、网红土味大字、表情僵硬、同一姿势换字。
```

Use when the user wants "好看", "大众", "可爱", "通用", "微信表情", or gives no preference.

## Preset 2: 漫画风格

Use when the user wants stronger emotion, comedy timing, or a more expressive illustrated look.

```text
漫画风格表情包：清晰手绘线条，夸张表情和肢体/物体变形，速度线、冲击线、汗滴、爆炸框、拟声符号适量使用，动作有漫画分镜感，表情冲突更强，画面有笑点但不杂乱，主体仍保持一致且缩略图可读。
避免：黑白草稿感、过多网点、复杂分镜框、恐怖猎奇、过度日漫脸、文字占满画面、动作乱到看不懂。
```

Good for animals, expressive mascots, angry/refusal/drama/eating-melon packs, and high-energy meme packs.

## Preset 3: 经典贴纸风格

Use when the user wants the clearest sticker-pack feel.

```text
经典贴纸风格：主体像独立贴纸剪纸一样清楚，厚实白边，干净透明背景，简化背景和道具，轮廓强，色块干净，表情动作一眼读懂，整体更轻、更Q、更适合直接作为聊天贴纸上传。
避免：复杂场景、背景插画感、过重光影、写实材质、边缘脏、白边不稳定、主体太小、细节太多。
```

Good for platform-ready static packs, small icons, simple animals, food, cans, and quick chat reactions.

## Preset 4: 强烈平面设计风格

Use when the user wants a more graphic, striking, or brand-like expression pack.

```text
强烈平面设计风格：高识别度平面图形，强轮廓，明确几何构图，大色块，高对比配色，少量有设计感的阴影或颗粒，画面像精致海报符号但仍是可发送表情，主体造型统一，文字和图形关系强。
避免：普通企业插画、信息图表感、复杂渐变、过多装饰纹理、品牌logo误用、主体被设计元素盖住、缺少表情包情绪。
```

Good for product-like subjects, cans/bottles, gadgets, brand-adjacent mascots, and packs that should look sharper or more distinctive.

## Preset 5: 古早QQ聊天风格

Use when the user wants a nostalgic early Chinese instant-messenger feeling: old QQ-era chat energy, glossy little icons, and playful desktop-chat emotion.

```text
古早QQ聊天风格表情包：怀旧即时通讯表情味道，圆润小图标感，轻微像素/低分辨率边缘趣味，亮晶晶高光，柔和渐变，蓝白聊天软件氛围，夸张但简单的表情，动作直接，符号化汗滴/爱心/星星/感叹号，像早期聊天窗口里会出现的小表情，但保持现代清晰度和可上传质量。
避免：直接复制QQ企鹅、QQ官方表情、QQ logo或受保护角色；不要做成真实软件截图，不要过度像素化到看不清，不要脏旧压缩噪点，不要低质网页小图，不要复刻具体历史表情包。
```

Good for nostalgic meme packs, animals with old internet humor, little object mascots, cans/drinks with chat-window jokes, and playful "上网冲浪" mood.

Keep the nostalgia as visual flavor, not as file-quality degradation. Final exports still need clean 512px masters, readable captions, stable identity, and polished edges.

## Preset 6: 自定义

Use only when the user wants to describe a style or provides a reference image.

Ask for a short style brief:

```text
请用一句话描述风格，或者给一张参考图。比如：复古漫画、像手帐贴纸、黑白线稿、像像素游戏、低饱和治愈系。
```

Even for custom styles, keep the universal sticker quality bar:

- Subject identity must stay stable.
- Each sticker must be readable at thumbnail size.
- Actions must be distinct and sendable.
- Text must be readable and not malformed.
- The pack must not become a loose illustration series with weak sticker utility.

## Caption Style

Default Chinese caption treatment:

- Short phrases, usually 2-5 Chinese characters.
- Rounded bold lettering, readable at 240px and still legible at thumbnail size.
- White outer stroke or sticker backing when needed.
- Place text near the action, not as a detached title below every sticker.
- Use integrated lettering when generation handles it well; otherwise keep captions sparse or post-add only when the platform/review artifact needs it.

Do not put text on every sticker. A good pack usually mixes captioned and text-free stickers.

## Prompt Style Lines

Use the selected preset's style line in generation prompts.

Preset 1:

```text
Style: mass-market modern cartoon sticker. linework: soft thick rounded outline, clean polished edges. shape_language: cute compact mascot proportions, plush-like but not childish. color_system: bright controlled warm palette, friendly mainstream colors. lighting_rendering: subtle dimensional lighting, soft highlights, smooth finish. background_space: minimal light background or transparent sticker space. motion_symbols: small stars/hearts/sweat only when useful. texture_finish: clean commercial sticker polish. caption_treatment: short rounded readable text only if needed. hard_negatives: not photorealistic, not cheap bubble style, not dark, not cyberpunk, not cluttered, not generic AI placeholder.
```

Preset 2:

```text
Style: expressive comic sticker. linework: confident hand-drawn black lines with varied pressure. shape_language: exaggerated squash, stretch, and facial emotion. color_system: punchy comic colors with strong contrast or controlled monochrome accents. lighting_rendering: flatter ink-and-color rendering, not soft toy shading. background_space: comic burst, panel energy, speed lines, impact marks. motion_symbols: sweat drops, shock symbols, vibration lines, dramatic punctuation shapes. texture_finish: printed comic/sticker finish, crisp and energetic. caption_treatment: comic-style short text only if needed. hard_negatives: not rough sketch, not cluttered manga page, not horror, not over-detailed, not text-heavy.
```

Preset 3:

```text
Style: classic clean sticker. linework: clear simple outline with stable thick white outer sticker border. shape_language: large centered subject, simple readable pose, fewer details. color_system: crisp clean colors with strong subject/background separation. lighting_rendering: minimal shading, clean flat-to-soft rendering. background_space: transparent or almost empty background, no scene. motion_symbols: only a few simple sticker symbols. texture_finish: die-cut sticker look, clean antialiasing, no dirty edges. caption_treatment: optional compact text close to subject. hard_negatives: no complex scene, no heavy rendering, no tiny subject, no noisy texture, no unstable border.
```

Preset 4:

```text
Style: bold flat graphic design sticker. linework: graphic edges, minimal outline or deliberate high-contrast contour. shape_language: simplified icon-like subject integrated with geometric composition. color_system: limited palette, high contrast color blocks, strong accent color. lighting_rendering: flat design, almost no soft shading, optional halftone/grain accent. background_space: bold abstract shapes, diagonals, circles, frames, poster-like negative space. motion_symbols: geometric arrows, blocks, rays, dots, pattern rhythm. texture_finish: clean vector/poster finish. caption_treatment: typography as graphic element only if needed. hard_negatives: not corporate stock illustration, not infographic, not random gradients, not logo misuse, not cute-only generic sticker.
```

Preset 5:

```text
Style: nostalgic early-2000s Chinese instant-messenger chat sticker. linework: rounded icon outline with soft pixel-era charm. shape_language: simple small emoticon-like mascot pose, direct and readable. color_system: blue-white digital chat palette with glossy accent colors. lighting_rendering: shiny highlights, soft gradients, glassy button-like finish. background_space: simple old chat bubble/window mood without real UI screenshots. motion_symbols: sparkles, sweat drops, hearts, tiny alert icons, question marks in retro chat style. texture_finish: clean high-resolution nostalgia, not degraded. caption_treatment: short rounded chat-emoticon text only if needed. hard_negatives: not copying QQ penguin, QQ logos, official QQ emoticons, or protected characters; not a real software screenshot; not blurry; not low-quality; not over-pixelated.
```

Preset 6:

```text
Style: follow the user's custom style description/reference while preserving sticker readability, subject identity, pack consistency, and platform usability. Extract the custom style into linework, shape language, color system, rendering, background, texture, and hard negatives before generating.
```

## Style Rejection Rules

Reject and regenerate when:

- The pack looks like a generic AI sticker sample rather than a finished public sticker pack.
- The subject is cute but lacks clear silhouette or chat readability.
- The rendering is too realistic, too plastic, too childish, too dark, too busy, or too niche for the selected preset.
- Captions dominate the sticker instead of supporting the reaction.
- The selected style changes strongly between stickers.
- Multiple stickers have the same pose, same camera angle, and same composition with different words.
