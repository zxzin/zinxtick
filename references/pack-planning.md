# Pack Planning

Use this file for sticker/expression-pack planning before generation, especially for 9+ item packs.

## One-Button Planning Mode

When the user only gives a subject, do not ask for a full creative brief. Use this default:

```text
Subject: user-provided subject
Audience: general Chinese chat users
Style: ask the 6-option style menu; default to preset 1 when the user says default/casual/no preference
Theme: ask the 7-option theme menu; default to preset 1 when the user says default/casual/no preference
Count: 16 for full pack, 9 for compact preview
Format: static 512x512 PNG masters, transparent finals
Captions: short Chinese only where useful
Production gate: 4-sticker sample pass before full production when practical
```

Only ask short follow-ups. The normal follow-ups are the style menu from `style-presets.md` and the theme menu from `theme-presets.md`. Ask anything else only if a missing answer blocks production, such as required platform, use of a real brand/logo, or whether an uploaded reference image should be followed strictly.

## Per-Item Action Plan

Create a table or manifest entries with these fields:

```text
id:
caption:
chat_use:
theme_link:
action:
subject_pose:
expression_or_state:
prop_interaction:
composition:
text_mode: integrated | speech_bubble | bottom_caption | none
variety_notes:
```

The `theme_link` field should explain how the item belongs to the selected theme or custom prompt. The `action` field must describe what the subject is doing, not only the emotion. "Angry" is weak. "Squeezes a tiny keyboard while steam bursts from the ears" is stronger.

## 4-Sticker Style Sample

For a new subject or uncertain style, create a 4-sticker sample before the full set:

1. One positive/high-energy item from the chosen theme.
2. One refusal/negative/social-boundary item from the chosen theme.
3. One tired/collapsed/low-energy item from the chosen theme.
4. One playful/teasing/funny item from the chosen theme.

This sample must prove:

- The subject identity holds across different emotions.
- The selected style preset looks polished and consistent.
- The selected theme is recognizable without long explanations.
- Captions, if present, are readable and not visually cheap.

If the sample fails, fix the identity lock, selected style line, theme interpretation, or action ideas before generating 9 or 16 items.

## Default 16-Pack Reaction Mix

Use this as a starting mix when the user gives only a subject:

1. 收到: confirms receipt with a clear gesture or prop.
2. 谢谢: grateful reaction, gift/heart/bow without overacting.
3. 好耶: celebration, bounce, confetti, raised prop, or fizz pop.
4. 加油: cheering, banner, megaphone, battery charge, or push motion.
5. 不行: refusal, crossed sign, shield, hiding, or blocking.
6. 你猜: playful tease, peek, mystery card, side-eye, or smug pose.
7. 无语: blank stare, collapsed posture, silence marks, or cold wind.
8. 吃瓜: watching drama with snack/prop; subject is actively observing.
9. 摸鱼: slacking, hiding behind screen/book/can tab, or drifting away.
10. 开摆: giving up dramatically, lying flat, melting, or rolling away.
11. 裂开: stress break, crack effect, fizz burst, or dramatic split metaphor.
12. 困了: sleepy, blanket, dim light, drooping posture, or slow wobble.
13. 抱抱: comfort, hug prop, two-character option, or soft recovery pose.
14. 冲: fast forward, rocket motion, speed lines, or energetic push.
15. 哈哈: laughing action without relying only on a mouth; use body bounce, tears, shake marks.
16. 晚安: sleeping, moon, blanket, lights-out, or curled-up rest.

Swap items to match the subject and audience. A cola can pack might use fizz, ice, straw, tab, spill, vending machine, and bubble gags. A tiger pack might use stripes, paws, tail, roar marks, and plush-like pounces.

## Subject-Specific Action Translation

Translate the default reactions into the subject's own physical language:

- Hamster: cheeks puff, tiny paws hold props, rolls into a ball, hides in bedding, nibbles seeds.
- Mouse/rat: peeks from a hole, tail flicks, carries crumbs, sneaks past, freezes in surprise.
- Tiger: tail swish, stripe blur, soft pounce, tiny roar marks, paw stamp, proud chest.
- Cat: loaf pose, tail curl, paw swipe, side-eye, box hiding, stretch collapse.
- Cola/can: pull tab pops, fizz bursts, condensation sweat, straw sip, dented collapse, vending-machine gag.
- Food: steam sigh, bite mark shock, sauce drip, wrapper blanket, plate stage, crumbs as motion marks.

Use props and motion marks as jokes, not as labels. The sticker should be understandable even if the caption is removed.

## Variety Checklist

Before generation, compare adjacent items and the full set:

- Body/object angle changes: front, side, diagonal, top-down, tilted, lying, bouncing, squeezed.
- Scale changes: close-up, full-body, tiny far pose, oversized prop, cropped dramatic pose.
- Expression/state changes: alert, blank, shocked, sleepy, proud, annoyed, shy, exhausted.
- Interaction changes: holding, hiding, pushing, sipping, blocking, peeking, dragging, stamping, falling, popping.
- Composition changes: left/right placement, foreground prop, behind-object reveal, motion arc, small scene, isolated cutout.
- Text changes: some integrated text, some no text, occasional speech bubble or bottom caption only when useful.

Reject the plan if many rows differ only by caption.

## Prompt Pattern

Use a prompt shaped like this:

```text
Create a cohesive sticker pack featuring [SUBJECT IDENTITY LOCK].
Format: [COUNT] separate square sticker designs arranged in a clean grid/contact sheet, each with enough margin for splitting.
Style: [chosen style], expressive chat sticker, clean silhouette, readable at small thumbnail size.
Theme: [chosen theme preset or custom prompt summary].
Identity: preserve [core silhouette/colors/features/materials]. Do not change [forbidden drift].
Variety: every sticker must show a distinct action and pose, not the same pose with changed captions.
Text: [caption rules], keep Chinese text short and readable; use no text where action is clear.
Items:
01 ...
02 ...
```

If generating one sticker at a time, keep the same identity lock and style line in every prompt and include that item's action-plan row.

## Contact-Sheet Review

Review the contact sheet before splitting:

- Squint or zoom out to thumbnail size.
- Ask whether every item is identifiable without reading filenames.
- Ask whether a normal chat user would actually send each sticker.
- Mark weak repeats for regeneration.
- Check that captions are readable and not misspelled.
- Check margins for later split/crop.
- Check that the subject still reads as the same subject across the full set.
