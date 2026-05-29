# Subject Identity

Use this file before generating sticker artwork for a new subject. The goal is to define what must stay stable while still allowing expressive meme actions.

## Identity Lock Template

Write a short identity lock before the first generation:

```text
Subject:
Category: animal | mascot | object | food | drink | product | other
Core silhouette:
Required colors/materials:
Required face/features:
Required object details:
Allowed expression mechanisms:
Forbidden drift:
Reference inputs used:
```

Keep it concrete. "Cute hamster" is too loose; "round golden hamster, tiny rounded ears, soft cream belly, black bead eyes, short paws, no long human arms" is usable.

## Animal Subjects

Preserve species cues:

- Hamster: round body, tiny rounded ears, small paws, cheek volume, compact posture.
- Mouse/rat: pointed snout, larger round ears, thin tail if visible, small paws.
- Tiger: orange coat, black stripes, rounded muzzle, ears, tail, strong but cute posture.
- Cat: triangular ears, whiskers, tail, paw shape, flexible body language.

Reject animal drift when:

- The species becomes ambiguous across the pack.
- The animal gains human hands, shoes, clothes, or limbs not requested by the user.
- Accessories hide the species cues.
- Motion marks, props, or shadows look like extra anatomy.

## Object, Food, Drink, And Can Subjects

Decide whether the object is:

- A pure object doing actions through squash, tilt, spill, pop, steam, condensation, dents, or motion.
- A personified object with a simple face and small limbs.
- A mascot-like object with consistent anatomy.

Preserve object cues:

- Can: cylinder silhouette, top/bottom rims, pull tab, label band, metallic highlights.
- Cola bottle/can: dark drink color cues, bubbles, fizz, red/brown palette only if user permits brand-like cues.
- Food: recognizable shape, surface texture, wrapper, garnish, steam, bite mark, or plate context.
- Tool/product: silhouette, key buttons, screen, handle, cap, nozzle, cable, or material.

Reject object drift when:

- The object turns into a generic blob, cup, robot, or unrelated mascot.
- A real brand mark appears without user-provided assets or permission.
- The label text becomes distorted and distracts from the sticker.
- Added limbs overpower the original object silhouette.
- The action cannot be understood without reading a caption.

## Product And Brand-Like Subjects

If the user supplies a brand/product reference, preserve the permitted visual assets. If not, make a fictional design with generic visual cues.

Do not copy protected characters, exact trademark logos, or distinctive packaging from real brands unless the user provided the assets and asks to work with them. When in doubt, use a generic parody-safe product identity.

## Stable Variation Rules

The subject may change pose, angle, emotion, scale, squash/stretch, prop interaction, and text treatment. It should not change:

- Species/object category.
- Main silhouette.
- Main color/material.
- Face placement and feature count.
- Product details that make it recognizable.
- Any user-stated forbidden element.

If a generation has a funny idea but weak identity, reject or regenerate it. Do not accept "cute but no longer the subject."
