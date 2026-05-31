# Generation Routes

Use the current AI Agent's built-in or configured image-generation model whenever it exists. The skill should adapt to its host environment:

- In Codex, use Codex's available image-generation tool.
- In Claude, use Claude's available built-in image-generation tool if that environment exposes one.
- In Antigravity, Qoder, or another Agent, use that Agent's configured image-generation tool.
- If the current Agent cannot render images, produce a generator-ready prompt pack instead of claiming finished files.

Do not hard-code one provider as the required route. The required behavior is the workflow, not a specific model brand.

## Route Selection

Choose the strongest available route and record it in `manifest.json` or `README.md`.

```text
generation_route:
native_image_model:
reference_input_status:
image_files_exist:
usable_for_platform_export:
notes:
```

Routes:

1. `agent_native_with_reference_input`: the current Agent's image model supports actual image/reference inputs. Best route for final artwork.
2. `agent_native_prompt_only`: the current Agent's image model accepts only text prompts. Usable for samples and possible finals after strict visual QA, but do not claim reference-image compliance.
3. `external_generator_prompt_pack`: the current Agent cannot render images, so it produces exact prompts for a separate image model.
4. `postproduction_only`: images already exist; current Agent handles split, resize, cutout, contact sheets, and platform packaging.

## Agent-Native Reference-Input Route

Use when the current Agent's image generator can actually accept reference images.

Required inputs:

- Subject reference image if provided.
- Style reference image if provided or selected.
- Accepted sample stickers if continuing a pack.
- Subject identity lock.
- Selected style preset.
- Selected theme preset or custom prompt.
- Per-item action plan.

Workflow:

1. Generate a 4-sticker sample sheet first.
2. Visually QA identity, style, theme, text, and variety.
3. Regenerate weak samples before full production.
4. Generate the full 16-sticker set, preferably as individual stickers or small batches if contact-sheet splitting is unreliable.
5. Land every accepted source file inside the active pack folder.
6. Record `generation_route: agent_native_with_reference_input` and `reference_input_status: actual_image_inputs`.

Do not say a reference was used unless it was actually sent as an input to the native image model.

## Agent-Native Prompt-Only Route

Use when the current Agent has an image generator but it accepts only text prompts.

Rules:

- Include the subject identity lock, style line, theme summary, and per-item action plan in the prompt.
- Label outputs as prompt-only until visual QA passes.
- If identity consistency is weak, switch to individual sticker prompts with repeated identity/style text.
- Record `generation_route: agent_native_prompt_only` and `reference_input_status: prompt_only_no_image_inputs`.

Prompt-only can produce useful samples, but it is more likely to drift across 16 items. Treat the contact sheet as a review artifact until split files pass QA.

## No-Image-Tool Route

Use when the current Agent cannot generate images directly.

Expected output:

- Subject identity lock.
- Selected style and theme.
- 4-sticker sample prompt.
- 16-item action plan.
- One full contact-sheet prompt.
- Optional per-sticker prompts for all 16 items.
- Negative prompt / rejection list.
- Platform folder and manifest plan.

Do not claim finished sticker files, transparent PNGs, or platform-ready assets until actual image files exist. Say clearly that the result is a generator-ready prompt pack.

This route should still be useful: another user or tool can paste the prompts into any capable image model, then return the images for post-production.

## Prompt Pack Format

When producing a handoff prompt pack, include:

```text
Pack brief:
Subject identity:
Style preset:
Theme preset/custom prompt:
Count:
Canvas:
Text rules:
Quality rules:
Negative rules:

4-sticker sample prompt:

Full-pack prompt:

Per-sticker prompts:
01 ...
02 ...
...
16 ...
```

For detailed user prompts, preserve user-required captions and scenes first. Fill missing items with matching theme reactions.

## Universal Negative Rules

Add these to all generation prompts:

- No real brand logos unless supplied by the user.
- No copied protected characters or official sticker assets.
- No repeated same pose with only caption changes.
- No malformed Chinese text; if text is unreliable, keep text minimal and make the action clear.
- No cluttered backgrounds, tiny subject, clipped props, broken limbs, or inconsistent subject identity.
- No claiming platform-ready status before exported files and QA exist.
