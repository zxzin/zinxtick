# Production And QA

Use this file after the action plan exists or when preparing sticker files for delivery.

## Quality Bar

The output must look like a public sticker pack, not just a technically valid image set.

Accept only when:

- The set looks cohesive and commercially usable.
- The subject is instantly recognizable in every sticker.
- The style is broadly friendly, polished, and not niche.
- Each sticker has a clear chat use case.
- The set has enough humor, movement, or emotional timing to be worth sending.

Reject when:

- It looks stiff, generic, ugly, over-rendered, plastic, noisy, or like an AI placeholder.
- The same pose is repeated with different captions.
- The subject identity drifts from sticker to sticker.
- A sticker needs a long explanation to understand.
- Text is malformed, too large, too small, or visually cheap.

## File Landing

For every pack, create an active output folder before post-production. Save or copy any generated source that might be used into `source/` immediately.

Do not treat chat thumbnails, temporary cache paths, or "latest generated image" lists as final source files. If the actual file cannot be opened from the active pack folder, regenerate or re-land it.

Record in `manifest.json` or `README.md`:

- Subject identity lock.
- Selected style preset or custom style brief.
- Selected theme preset or custom theme prompt.
- Output count.
- Generation route: reference-image input, prompt-only generation, local drawing, or mixed.
- Accepted source files.
- Rejected source files and reasons when useful.
- Final export folders.
- Platform assumptions and status.

## Splitting And Masters

Split only after the source sheet passes visual review.

- Do not assume a generated grid is perfectly even. Detect or manually verify boundaries.
- Preserve margin around props, text, motion marks, ears, tails, tabs, caps, fizz, shadows, and effects.
- Build independent 512x512 PNG masters first.
- Rebuild a contact sheet from the split master files and inspect it, not only the original source sheet.
- If a single sticker needs correction, update its master and rebuild the contact sheet.

## Transparent Cutouts

For static stickers, transparent-background PNGs are usually the preferred final variant unless the platform or user asks for an opaque background.

- Keep accepted opaque/source masters as backup.
- Remove only the outer/background area with edge-flood or structured masking.
- Do not globally delete all white pixels; preserve eyes, highlights, white text strokes, labels, foam, paper, steam, shine, and intentional outlines.
- Verify RGBA mode, mixed alpha values, no clipped subject, no accidental holes, no rough halo, and no dark-mode fringe.
- Create a checkerboard preview/contact sheet before replacing downstream platform exports.

## Platform Exports

When the user asks for a specific platform, verify current platform requirements if they may have changed.

Common static output flow:

```text
split/masters_512/       accepted 512px masters
transparent_512/         transparent final cutouts
platform/<platform>/     upload-size variants
contact-sheet/           review grids and comparison sheets
```

For WeChat-style packs, common assets may include main sticker files, album cover, chat icon, and detail banner. Treat cover/icon/banner as designed assets, not blind mechanical crops:

- Chat icon must remain readable at tiny size and usually needs transparent background.
- Detail banner should be a polished text-free scene unless the platform explicitly asks otherwise.
- Do not claim submission unless the platform accepted the files.

## WeChat-Ready Static Pack

When the user wants a complete WeChat-ready pack, produce a full asset folder, not only source images or a contact sheet.

Default static WeChat folder:

```text
source/                         accepted generated/source artwork
split/masters_512/              16 final 512x512 PNG masters
transparent_512/                transparent 512x512 PNG final cutouts
wechat/single_main_240/         16 main 240x240 PNG upload images
wechat/cover_240/               240x240 album cover
wechat/chat_page_icon/          50x50 transparent PNG chat icon
wechat/detail_banner/           750x400 JPG or PNG detail banner
contact-sheet/                  final review sheet, checkerboard transparency sheet, WeChat preview sheet
manifest.json                   subject, style, theme, item list, file list, dimensions, status
README.md                       upload notes, assumptions, revision history, QA summary
```

WeChat asset rules:

- Main stickers: derive from accepted 512 masters after visual QA, not from rejected sheets.
- Cover: use one strong pack-representative pose or a dedicated simple cover composition.
- Chat page icon: simplify one accepted sticker or generate a matching icon; no captions, no clutter, readable at 50px.
- Detail banner: make a theme-specific 750x400 scene; do not use visible text unless current platform rules explicitly require it.
- Do not crop caption fragments out of sticker cells to make cover/icon/banner if the result looks patched or dirty.
- Rebuild all previews from the latest final files after any replacement.
- Do not claim the pack is submitted unless WeChat accepted it in the browser/platform.

## Animated Stickers

For animated stickers, create one motion sample before producing the full set.

- Define frame count, grid layout, duration, loop behavior, and target platform constraints.
- Preserve subject identity across every frame.
- Use anticipation, contact/hold, recoil, secondary motion, and settle; avoid tiny unclear movement.
- Split frames only after verifying cell boundaries.
- Normalize frame alignment without killing intentional motion.
- Decode exported GIF/APNG/WebP back into a preview sheet to check palette, alpha, jitter, clipping, and timing.

## Final QA Gate

Do not deliver as finished until these checks pass:

- File count matches the requested pack count.
- Dimensions and formats match the stated target.
- The latest corrected files are used, not stale exports.
- Every sticker reads at 512px, 240px, and thumbnail size.
- The subject identity is stable across the set.
- The selected theme is visible across the set; it is not just random generic reactions.
- Text is readable, correctly spelled, and stylistically consistent.
- Pack-level variety is strong enough for chat use.
- At least 80% of the stickers feel immediately sendable to a normal chat user; weak filler items are redesigned.
- Transparent previews have no unwanted square backgrounds, holes, halos, or clipped props.
- WeChat-ready packs include main 240 images, cover, chat icon, detail banner, contact sheets, manifest, and README.
- Contact sheets and individual final files have been opened or rendered for visual inspection.

If a result is useful but not final, label it as a draft, rejected sample, or review artifact.
