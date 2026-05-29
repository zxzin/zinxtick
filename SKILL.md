---
name: zinxtick
description: Beginner-friendly generic sticker and meme-pack production workflow. Use when turning a user-provided character, animal, mascot, product, food, drink, can, object, logo-like subject, or original visual concept into a cohesive WeChat-ready static or animated sticker/expression pack, including built-in style preset selection, theme preset selection or custom prompt handling, item planning, image-generation prompting, contact sheets, transparent cutouts, WeChat export assets, and visual QA.
---

# Zinxtick

Use this skill to make sticker packs from an arbitrary subject, not only from a fixed mascot. The subject may be an animal, personified object, product container, food, drink, brand mascot, original character, or user-provided reference image.

The goal is a complete submit-ready sticker asset set: each sticker must work as a distinct chat reaction, preserve the subject's identity, follow the chosen style and theme, and survive WeChat/platform thumbnail review.

## Simple Operator Flow

For ordinary users, run this flow without asking them to solve art direction from scratch:

1. Read the user's subject in one sentence: "make stickers for a hamster", "make cola-can memes", "make a tiger expression pack".
2. If the user did not specify style, ask one short preset question: "选风格：1大众通用美术 2漫画风格 3经典贴纸风格 4强烈平面设计风格 5古早QQ聊天风格 6自定义；不选默认1。"
3. If the user did not specify a theme or detailed prompt, ask one short theme question: "选主题：1日常高频 2打工摸鱼 3阴阳怪气 4可爱贴贴 5吃喝玩乐 6节日祝福 7自定义详细提示；不选默认1。"
4. Build a subject identity lock: what must stay recognizable in every sticker.
5. Pick the default count: 16 stickers for a full WeChat-ready static pack, or 9 only when the user asks for a compact preview.
6. Write the per-item action plan from the selected theme or custom prompt. Do not generate from captions alone.
7. Choose the available generation route. Prefer the current AI Agent's built-in or configured image-generation model; use reference-image inputs when that model supports them. If the current environment has no image generator, create a generator-ready prompt pack and do not claim images were produced. See `references/generation-routes.md`.
8. Produce a small style/theme sample pass first when the subject, style, or custom prompt is new, unfamiliar, branded, or high-risk. Use 4 representative stickers.
9. Reject weak samples instead of continuing. Fix identity, style, theme, and action variety first.
10. Generate the full set only after the direction is strong enough.
11. Review the contact sheet at thumbnail size. Regenerate repetitive, ugly, off-subject, off-theme, or unreadable stickers.
12. Export WeChat-ready masters, transparent cutouts, contact sheets, main sticker files, cover, chat icon, detail banner, manifest, and README after visual acceptance.

The default behavior should feel like a guided one-button pack builder: the user provides the subject, chooses style and theme numbers if they care, and Codex handles the reaction mix, prompt strategy, QA, and WeChat asset export sequence.

## Default Assumptions

When the user gives only a subject, proceed with these defaults unless the request implies otherwise:

- Static sticker pack.
- 16 stickers for a full WeChat-ready pack, or 9 stickers only for a compact review set.
- 512x512 PNG masters.
- Transparent final cutouts after the artwork is accepted.
- A contact sheet for review before WeChat/platform packaging.
- Style preset: ask the 6-option menu when absent; use preset 1 if the user says "默认", "随便", "大众", or does not care. See `references/style-presets.md`.
- Theme preset: ask the 7-option menu when absent; use preset 1 if the user says "默认", "随便", "日常", or does not care. See `references/theme-presets.md`.
- Chinese short captions only when they materially improve the meme beat; no caption when the action reads clearly.

If the target platform is stated, follow its current requirements. For unstable platform rules, verify current size, format, count, alpha, file-size, and upload constraints before claiming readiness.

## Core Workflow

1. Identify the subject, target platform, output count, static vs animated format, final vs concept-review status, caption language, forbidden elements, and any reference images/assets.
2. Create a subject identity lock before generation. Capture the non-negotiable silhouette, color/material, face/feature layout, proportions, and allowed exaggerations. See `references/subject-identity.md`.
3. Select a style preset from the built-in menu. Ask only the compact style menu if the user has not chosen one; ask for free-form style only when they choose preset 6. See `references/style-presets.md`.
4. Select a theme preset from the built-in menu, or parse the user's detailed prompt as the theme source. Ask only the compact theme menu if no theme exists; ask for free-form detail only when they choose preset 7. See `references/theme-presets.md`.
5. Write a per-item action plan before batch generation for 9+ stickers. Each item needs a chat use case, action, pose/expression change, prop interaction, composition, text mode, and theme link. See `references/pack-planning.md`.
6. Select and record the generation route. Use the current AI Agent's built-in or configured image-generation model when available; use reference inputs only if that model supports them; use prompt-pack handoff when the current tool cannot render images. See `references/generation-routes.md`.
7. Generate or draw source artwork using the identity lock, style preset, theme, and action plan. Use reference-image inputs when the tool truly supports them; otherwise label results as prompt-only concept drafts.
8. Review the full set at thumbnail size before splitting, resizing, cutout, upload prep, or final delivery.
9. Land accepted source files inside the active pack folder before post-production. Do not treat image-generation cache paths as source of truth.
10. Split/crop/resize only after visual acceptance. Build 512 masters first, then platform variants.
11. Make transparent cutouts with edge/background masking, not by globally deleting white pixels.
12. Build WeChat-ready package assets: main sticker files, cover, chat page icon, detail banner, contact sheets, manifest, and README.
13. Rebuild final contact sheets from the latest exported files and inspect them visually.
14. Report only existing output paths and clearly label concept drafts, prompt-pack handoff, review-ready assets, publish-ready files, or submitted/accepted platform status.

## Hard Gates

- A pack cannot be accepted if it is one pose with swapped captions or nearby props.
- Every sticker must read as a distinct chat action at thumbnail size.
- For 9-, 16-, or 24-sticker packs, each item must vary at least three of: body/subject angle, scale, expression, eye/gaze direction, hand/limb/tab/cap placement, prop interaction, composition, motion marks, symbols, foreground/background layout, or timing beat.
- A prop label is not enough. The prop must create action or comedy: hiding, sipping, blocking, peeking, stamping, melting, exploding, squeezing, dragging, celebrating, refusing, recovering, or another readable beat.
- If three or more stickers share the same subject angle, expression, placement, and action logic, reject and redesign the repetitive items before export.
- Do not package or call a set final while pack-level variety fails.
- Do not ask open-ended art-direction questions by default. Offer the 6 style presets; only collect custom style text when the user chooses preset 6.
- Do not ask open-ended theme questions by default. Offer the 7 theme presets; only collect custom theme detail when the user chooses preset 7 or already gave a detailed prompt.
- If the user provides a detailed prompt, treat it as the highest-priority theme brief and only fill missing slots with default logic.
- Do not claim native/reference-input generation unless the current AI Agent's image-generation route actually accepted image/reference inputs.
- Do not claim a no-image-tool run produced finished sticker files. In those environments, produce a prompt pack, manifest plan, and post-production instructions until real image files exist.
- Do not accept technically correct but ugly, stiff, low-energy, or AI-placeholder-looking stickers.
- Do not call a pack WeChat-ready without main sticker files, cover, chat icon, detail banner, contact sheet, manifest, README, and visual QA.
- Do not claim reference-image compliance unless the generation route actually accepted and used image inputs.
- Do not silently overwrite accepted outputs. Create comparison variants when changing cutout, scale, background, or platform exports.

## Subject Rules

Build rules from the current subject rather than importing fixed-mascot anatomy. Examples:

- Animal: preserve species cues such as ear shape, snout, whiskers, stripes, tail, posture, and body proportions.
- Object or food: preserve silhouette, material, opening mechanism, label zone, cap/tab/straw/pull ring, texture, and recognizable scale cues.
- Product or branded item: preserve only user-provided or permitted brand assets. If no brand asset is supplied, make a fictional/generic design instead of copying a real trademark.
- Original mascot: preserve the user-defined identity lock and avoid adding anatomy or accessories that change the character read.

For detailed subject templates and rejection rules, load `references/subject-identity.md`.

## Text And Captions

- Keep sticker captions short: often 2-5 Chinese characters, or a very short phrase.
- Prefer integrated sticker lettering generated with the artwork when it is readable and stylistically consistent.
- Use no text when the expression/action already communicates the reaction.
- Avoid detached bottom labels as the default; use them only when they improve recognition or match the chosen style.
- Reject unreadable, malformed, or semantically wrong generated text instead of pretending it is acceptable.
- Do not force one global text layout across the pack. Plan `text_mode` per item: `integrated`, `speech_bubble`, `bottom_caption`, or `none`.

## Output Structure

Create a dated pack folder in the user's project or another obvious working location:

```text
<project-or-output-root>/<pack-id>/
  source/
  split/original/
  split/masters_512/
  transparent_512/
  wechat/single_main_240/
  wechat/cover_240/
  wechat/chat_page_icon/
  wechat/detail_banner/
  contact-sheet/
  manifest.json
  README.md
```

For quick concept work, at minimum keep `source/`, `contact-sheet/`, and a short README/manifest note that records subject, count, generation route, accepted/rejected status, and output paths.

## References

Load only the reference needed for the current task:

- `references/subject-identity.md`: how to lock identity for animals, mascots, objects, food, drinks, cans, and product-like subjects.
- `references/style-presets.md`: built-in style menu, prompt style lines, and custom-style fallback.
- `references/theme-presets.md`: built-in theme menu, default 16-item theme sets, and detailed-prompt mode.
- `references/generation-routes.md`: agent-native image generation route, reference-input handling, prompt-only fallback, no-image-tool handoff, and required route labels.
- `references/pack-planning.md`: action-plan schema, variety checks, starter reaction sets, and prompt patterns.
- `references/production-qa.md`: file landing, split/crop/resize, transparency, platform exports, animated sticker notes, and final QA.
