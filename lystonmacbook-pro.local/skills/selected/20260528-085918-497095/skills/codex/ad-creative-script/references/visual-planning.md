# Visual Planning And Storyboard Craft

Use this when a script needs clearer visual expression, storyboard planning, shot design, director treatment, or AI image/video generation. The goal is to turn the idea into frames a director, storyboard artist, client, or image model can understand.

## Source-Based Principles

Condensed from commercial storyboard and shot-list practice:

- Start from a script, then make a shot list before final storyboard frames.
- Every storyboard frame needs clear notes for action, sound/dialogue, lighting, camera, and any extra production notes.
- Shot size, camera angle, and movement change the meaning of a scene; choose them to express the beat, not as decoration.
- Use arrows or motion notes to show character movement, object movement, camera movement, transitions, and visual transformation.
- Keep storyboard images readable; one frame should show one decisive moment.
- Storyboards are planning tools: they should expose gaps in the story before production.

## Visual Translation Gate

Before writing storyboard frames, fill:

```text
Core visual metaphor:
Recurring visual asset:
Visual progression:
Color / light arc:
Camera language:
Product visibility rule:
Motion grammar:
Transition rule:
End-frame composition:
```

For grounded cinematic realism, also fill:

```text
Observed real location:
Character bible summary:
Scene bible summary:
Real texture details:
Performance restraint:
Motivated light sources:
Ambient sound bed:
Behavioral turning point:
What remains unsaid:
```

Reject the plan if:

- The visual metaphor appears only in a few hero shots.
- The middle can be understood only through VO.
- Product placement is not planned shot by shot.
- Every shot uses the same scale, angle, or movement.
- There is no visual progression from opening to ending.
- Realism mode becomes generic lifestyle footage with no pressure, behavior, or sensory specificity.
- Characters are described only by beauty/style labels rather than behavior, wardrobe logic, hand habits, and social context.
- Locations lack used details, spatial obstacles, offscreen world, or product's natural place in the room.

## Shot Card Template

Use for commercial storyboard output:

```text
Shot:
Time:
Narrative job:
World-rule event:
Frame image:
Shot size:
Camera angle:
Camera movement:
Lens / focus:
Composition:
Action:
Product placement:
Lighting / color:
Sound / VO / supers:
Transition:
AI keyframe prompt:
```

Director storyboard rows should normally be 1.5-4 seconds. A 6-second range is a script beat, not a finished production storyboard row, unless the creative explicitly requires a long take and the row explains the camera movement, blocking, and transition.

For AI image/video workflows, add a `生成画面拆分` field to every storyboard row:

```text
生成画面拆分:
- 生成数量:
- A timepoint / type / single image:
- A handoff / transition:
- B timepoint / type / single image:
- B handoff / transition:
- C timepoint / type / single image:
- C handoff / transition:
```

This field is mandatory when the user complains that a storyboard row contains too much content, or when outputting image-generation keyframes.

## AI Keyframe Timing

Director shots and AI image keyframes are different deliverables. A director shot can last several seconds because it describes performance, camera travel, and edit rhythm. An AI image keyframe must describe one still, generatable moment.

For AI image generation:

- Use exact timepoints or intervals no longer than 2 seconds.
- Treat `00-06s`, `06-13s`, and similar ranges as invalid image-prompt rows and too broad for normal storyboard-image planning.
- Split every director shot longer than 2 seconds into setup, product/action contact, reaction, consequence, or transition keyframes.
- Do not put an entire movement, emotional arc, or before/after transformation into one keyframe.
- If a row needs "and then", split it.

Use this table structure for AI keyframes:

```text
Timepoint:
Keyframe type:
Narrative job:
Single image moment:
Shot size / angle:
Camera movement intent:
Motion handoff to next keyframe:
Transition in:
Transition out:
Product role:
AI image prompt:
```

Camera movement intent names what the eventual video move should feel like: static hold, slow push-in, pull-back reveal, pan, tilt, handheld drift, tracking, dolly/slide, rack focus, macro drift, locked-off graphic match, or whip pan. Motion handoff explains how the next frame connects: subject direction, camera direction, object motion, light change, focus shift, or sound bridge. Transition in/out states the edit grammar: hard cut, cut on action, match cut, graphic match, sound bridge, rack-focus handoff, whip pan, dissolve, fade, or end-frame lock.

Reject the keyframe table if any row:

- Covers more than 2 seconds.
- Contains multiple sequential actions.
- Has no camera movement intent.
- Has no transition in/out logic.
- Cannot be generated as a single independent still image.
- Does not state how many images to generate and what each image is when used inside a storyboard row.

## Shot Size Functions

Use shot size to express meaning:

| Shot size | Use when |
| --- | --- |
| EWS / extreme wide | Show scale, isolation, world rule, environment transformation. |
| WS / wide | Show relationship between subject and fantasy environment. |
| FS / full shot | Show body action, movement, ritual, choreography. |
| MS / medium | Show human behavior and product interaction together. |
| MCU / medium close-up | Show emotion while preserving context. |
| CU / close-up | Show product, hand, face, texture, exact action. |
| ECU / extreme close-up | Make a detail iconic: powder, spoon, label, button, eye, texture. |
| OTS / over-the-shoulder | Put audience into the user's decision or discovery. |
| POV | Let audience experience the world rule directly. |
| Insert | Clarify a prop, label, UI, pack, or causal detail. |

## Camera Angle Functions

| Angle | Use when |
| --- | --- |
| Eye level | Neutral, honest, human, grounded. |
| Low angle | Make object/child/world feel large, powerful, strange, or mythic. |
| High angle | Show vulnerability, pressure, systems, maps, or oversight. |
| Overhead | Show layout, process, transformation, ritual, or system logic. |
| Dutch angle | Show imbalance, sickness, confusion, unstable world rules. |
| Macro | Turn product material or tiny detail into a world. |

## Camera Movement Functions

| Movement | Use when |
| --- | --- |
| Static | Let impossible action speak; good for deadpan surrealism. |
| Slow push-in | Reveal realization, pressure, emotional focus. |
| Pull-back | Reveal scale, hidden system, or world-rule context. |
| Tracking | Follow a journey, process, or continuous transformation. |
| Dolly / slide | Show relationship changes between product and world. |
| Whip pan | Connect cause and effect quickly; good for comedy or rhythm. |
| Tilt | Reveal vertical scale, transformation, or power shift. |
| Match cut | Connect product action to world-rule consequence. |
| Rack focus | Move attention between product, user, and transformed world. |

## Visual Progression

Each script should progress visually:

1. **Disruption**: show what is wrong or unstable.
2. **Discovery**: reveal the world rule.
3. **Mechanism**: show product participating in the rule.
4. **Escalation**: show the rule acting on a larger or stranger scale.
5. **Resolution**: land on a simple, ownable end frame.

Do not repeat the same visual trick. Each beat must change the scale, stakes, or understanding of the system.

## Grounded Cinematic Realism Progression

For realism mode, progress through behavior instead of spectacle:

1. **Observation**: a specific real place and pressure.
2. **Accumulation**: small details reveal what the character is carrying.
3. **Routine / product entry**: product enters without feeling staged.
4. **Micro-shift**: one behavior, breath, look, or decision changes.
5. **Afterimage**: a quiet frame leaves the brand truth behind.

Use:

- Motivated light: window, kitchen lamp, phone, refrigerator, bathroom mirror, shop sign.
- Environmental blocking: doorways, counters, shelves, sinks, back seats, elevators, clinic corridors.
- Imperfect textures: receipts, water marks, fingerprints, half-open drawers, worn table edges.
- Natural sound bridges: kettle click to spoon tap, phone vibration to elevator hum, child breath to room tone.
- Character blocking: distance to door/window/product/phone, whether the character crosses a threshold, half-turns away, or avoids eye contact.
- Set dressing with behavioral evidence: receipts, half-open drawer, worn counter edge, damp umbrella, work badge, imperfect garment, product seal.

Avoid:

- Slow motion as a substitute for emotion.
- Perfectly clean, stock-like homes.
- Overwritten VO explaining what the actor already shows.
- Abstract "cinematic" terms without shot-specific decisions.

## Product Visibility Rule

Plan product presence:

- **Tease**: before full reveal, use color, shape, sound, pack silhouette, material, or ritual.
- **Causal reveal**: show exactly how product action triggers the world rule.
- **Proof/role**: product should be visible during the beat where it matters, not only after.
- **End frame**: pack/product should sit in the visual world, not pasted onto a separate beauty shot.

## AI Prompt Upgrade

For each keyframe prompt, specify:

- Aspect ratio and format.
- Product reference and placement.
- Character continuity.
- Exact decisive moment.
- Foreground/midground/background.
- Shot size, angle, movement implication.
- Lighting and color.
- Text/logo safe area.
- Negative constraints.
- Camera movement intent and transition in/out.

Avoid prompts that describe a whole scene arc instead of one frame.

Before writing AI prompts, decide whether each director shot needs 1, 2, or 3 keyframes:

- **1 keyframe**: static product/character moment with no internal change.
- **2 keyframes**: setup plus consequence, or action plus reaction.
- **3 keyframes**: setup, product/action contact, and transformed/resolved state.

Use 3 keyframes for shots involving product use, character emotional shift, reveal, transformation, or complex camera movement.

## Storyboard Quality Check

Before final output, ask:

1. Can someone sketch this frame from the description?
2. Does this shot have a clear narrative job?
3. Is the product placement intentional?
4. Does camera choice express meaning?
5. Does the transition clarify cause and effect?
6. Does the shot advance the world rule, not merely illustrate it?
7. Would this frame still be understandable with VO muted?
8. If this is for image generation, is the frame too overloaded for one image prompt?
9. Should this director shot be split into setup/action/consequence keyframes?
