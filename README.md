# Zinxtick

Zinxtick is an AI agent skill for turning a character, animal, product, food, drink, can, object, mascot, or visual idea into a themed sticker pack.

It is designed for agents that support local skills or reusable instruction folders, including Claude-style agents, Antigravity-style agents, Codex, and similar agent workspaces.

## What It Does

Give Zinxtick a subject:

```text
Make a sticker pack for a cat.
Make cola-can reaction stickers.
Make a tiger meme pack in a comic style.
Make a water-bottle sticker pack for work chat.
```

The skill guides the agent through:

- subject identity locking
- style preset selection
- theme preset selection
- per-sticker reaction planning
- image-generation prompts
- pack-level QA
- sticker export structure
- platform-ready asset preparation

## Presets

Style presets:

1. Mainstream cartoon
2. Comic
3. Classic sticker
4. Bold graphic design
5. Retro early-chat emoticon
6. Custom style

Theme presets:

1. Everyday reactions
2. Work and procrastination
3. Playful sarcasm
4. Cute and affectionate
5. Food, drinks, and fun
6. Greetings and holidays
7. Custom theme prompt

If the user writes in English, the agent should ask questions in English. If the user writes in Chinese, it should use the Chinese preset menus.

## How To Use

Copy this repository into the skills or instruction directory used by your AI agent, then invoke it by name:

```text
$zinxtick
```

Example:

```text
Use $zinxtick to make a sticker pack for a hamster.
```

If your agent does not support `$skill` syntax, point it at `SKILL.md` and ask it to follow the Zinxtick workflow.

## Output

A full run should produce a working pack folder with source images, contact sheets, accepted sticker files, transparent variants, platform-size exports, a manifest, and a short README for the generated pack.

The exact image-generation route depends on the agent you use. Zinxtick tells the agent to use its built-in or configured image-generation model when available. If no image generator is available, it should produce a generator-ready prompt pack instead of pretending finished images exist.

## Repository

GitHub: `github.com/zxzin/zinxtick`
