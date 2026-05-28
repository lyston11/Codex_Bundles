# Storyboard And AI Prompts

## Script Beats vs Director Storyboard vs AI Keyframes

Separate these outputs:

- **Script beat outline**: a writing layer. One beat may cover 4-8 seconds because it summarizes story progression, dialogue, and brand logic. Do not use this layer as storyboard or image prompts.
- **Director storyboard / shot list**: a production-planning layer. Default to 1.5-4 seconds per shot for normal commercial storyboards, with shot size, angle, camera movement, blocking, sound, and transition notes. Use longer shots only when the user explicitly asks for a compact outline or an intentionally long-take film.
- **AI keyframe package**: one image prompt must describe one still moment only. It should not carry a full 8-second action, emotional arc, or before/after transformation. AI image rows use exact timepoints such as `00:01.5` or intervals no longer than 2 seconds such as `00:01-00:02.5`.

When the user will generate images, always decompose director shots into AI keyframes. Rows like `00-06s`, `06-13s`, or `13-20s` are valid only as script beat outline timing; they are invalid as director storyboard rows for image planning and invalid as AI image keyframes or image prompts.

If the user asks for 生图, 分镜生图, AI keyframes, image prompts, storyboard images, Nano Banana prompts, Midjourney prompts, or video-generation frames, default to the expanded AI keyframe package even if a compact director storyboard is also included.

## Hard Timing Rule For Image Generation

For AI image generation:

- Prefer exact keyframe timepoints: `00:00.0`, `00:01.5`, `00:03.0`.
- Use short intervals only when needed for edit rhythm; never exceed 2 seconds.
- Any director shot longer than 2 seconds must be split into setup / product contact or action / reaction or consequence keyframes.
- Any row with multiple beats, "and then", "before/after", "walks in and sprays and city changes", or more than one emotional state must be split.
- A 30s film normally needs at least 16 AI keyframes; 60s normally needs at least 28 AI keyframes.
- If you output both layers, label them clearly as `Director Shot List` and `AI Image Keyframes`. Never let a director shot row double as an AI image prompt row.

Each AI keyframe row must include:

```text
Keyframe time:
Type: hero / continuity / transition / end-frame
Narrative job:
Single visual moment:
Shot size / angle:
Camera movement intent:
Motion handoff to next keyframe:
Transition in:
Transition out:
AI image prompt:
Negative constraints:
```

If one of these fields is empty, the keyframe is not finished.

## Storyboard Row Image Split Column

When producing a storyboard table for AI image/video work, every director-storyboard row must include a `生成画面拆分` column. This column tells the user exactly how many still images to generate for that row and what each image should contain.

Use this compact pattern inside the table cell:

```text
生成 2 张：
A 00:01.0｜setup｜单一画面描述｜承接：从上一帧...｜转场：...
B 00:02.0｜action/reaction｜单一画面描述｜承接：A 的...｜转场到下一行：...
```

Rules:

- A row with one stable still moment may generate 1 image.
- A row with product touch, character decision, synchronized crowd action, camera reveal, location change, or emotional shift usually generates 2 images.
- A row with setup + action + consequence must generate 3 images.
- Do not hide multiple images inside a single sentence. Label them A/B/C.
- Each generated image description must be an independent still, not a mini-scene.
- Each generated image must include its handoff: what visual, motion, sound, object, light, or direction connects it to the previous/next image.
- The table row's `画面 / 表演` may summarize the director beat, but `生成画面拆分` must be granular enough for direct image generation.

Prefer this row structure:

```text
时间
导演意图
画面 / 表演
生成画面拆分
运镜 / 承接 / 转场
声音 / 文案
```

If the user says the storyboard is too dense, overloaded, or not usable for image generation, rewrite the storyboard using this structure before writing new creative content.

## AI Keyframe Decomposition Rule

Split any director shot into multiple keyframes when it contains more than one of:

- Location change
- Camera movement reveal
- Character action change
- Product action
- Emotional shift
- Object transformation
- Before/after contrast
- Text/logo/end-frame requirement
- Multiple important subjects
- Complex world-rule consequence

Use this decomposition pattern:

```text
Director shot:
Shot duration:
What changes during the shot:
AI keyframe A - setup / state before:
AI keyframe B - decisive action / product contact:
AI keyframe C - consequence / resolved state:
Camera movement handoff:
Transition into next shot:
```

Do not ask an image model to show "walks in, sprays perfume, city notices, then end frame" in one image.

## Camera Movement And Transition Grammar

Every director shot and AI keyframe package must have an edit plan. For AI keyframes, describe the movement as intent or handoff, because the image itself is still.

Camera movement intent options:

- Static hold: let performance, product, or composition carry the beat.
- Slow push-in: pressure, realization, intimacy, or product significance increases.
- Pull-back reveal: hidden context or scale becomes visible.
- Pan / tilt: discovery across horizontal or vertical space.
- Handheld drift: realistic presence, nervousness, documentary texture.
- Tracking / dolly / slide: follow a journey, ritual, or relationship shift.
- Rack focus: attention moves from person to product, product to consequence, or foreground to background.
- Macro drift: turn material, label, spray, powder, skin, fabric, or liquid into a tactile world.
- Locked-off graphic match: prepare a visual rhyme for the next frame.
- Whip pan / swish pan: high-energy transition, useful only when motion blur and direction are planned.

Motion handoff options:

- Subject movement direction: left-to-right, toward lens, away from lens, crosses doorway, hand enters frame.
- Camera movement direction: push-in continues, pan exits right, rack focus lands on product.
- Object motion: cap twist, bottle lift, powder fall, fabric movement, steam, light flicker.
- Light change: window flare, sign glow, refrigerator light, streetlight sweep.
- Sound bridge: spoon tap, spray hiss, footsteps, room tone, music cue continues.

Transition options:

- Hard cut: when the next image is already clear and contrast matters.
- Cut on action: the same action continues across two angles.
- Match cut / graphic match: shape, color, line, composition, gesture, or product silhouette rhymes across shots.
- Sound bridge / J-cut / L-cut: sound starts before the image or carries over after the cut.
- Rack-focus handoff: focus landing point becomes the next shot's subject.
- Whip pan transition: blur direction and landing composition must be specified.
- Dissolve: use sparingly for memory, time passage, or sensory blending.
- Fade / end-frame lock: for final packshot or emotional afterimage.

## Storyboard Frame Fields

Use this for each frame:

```text
Shot / Frame:
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
Product detail:
Character continuity:
Character lived-in detail:
Hand / body behavior:
Wardrobe logic:
Lighting / color:
Sound / VO / supers:
Scene used detail:
Motivated light source:
Ambient sound implied:
What is unsaid:
Transition:
Text / logo safe area:
AI keyframe prompt:
Motion prompt:
Avoid:
```

## Continuity Checklist

Before writing prompts, lock:

- Product reference: shape, color, packaging, label placement, material, scale.
- Character bible: age range, face continuity, hair, wardrobe logic, body habit, hand behavior, emotional restraint, lived-in imperfection.
- World rules: era, location, weather, color palette, surreal rules.
- Visual motif: repeated object, light, gesture, line, or transformation.
- Scene bible: real location, motivated light, used details, foreground/midground/background, spatial obstacle, product's natural place.
- Camera language: handheld, locked-off, macro, tracking, match cut, overhead, etc.
- End frame: product, brand space, CTA/slogan space, background simplicity.

## AI Keyframe Prompt Pattern

```text
广告分镜关键帧，{brand/category}，{frame purpose}。
主体：{product/character with continuity details}。
场景：{specific setting and world rule}。
动作/瞬间：{single decisive moment, not a whole story}。
镜头：{shot size, camera angle, implied movement, lens/focus}。
构图：{foreground, midground, background, product position, text/logo safe area}。
光影色彩：{lighting, palette, texture}。
风格：{cinematic / premium / documentary / surreal but realistic / UGC}。
质量：high-end commercial photography, realistic materials, coherent hands, accurate product geometry。
避免：extra text, wrong logo, distorted packaging, duplicated fingers, uncanny faces, cluttered background。
```

For character prompts, avoid "beautiful", "handsome", "perfect", "model-like", "smiling family", and generic "elegant". Use behavior, wardrobe logic, lived-in details, and restrained performance instead.

For scene prompts, avoid "luxury apartment", "cozy home", "cinematic room", and "premium lifestyle background" without concrete used details and motivated light.

## Video Motion Prompt Pattern

```text
Duration: {seconds}
Start frame:
End frame:
Camera:
Action:
Product continuity:
Character continuity:
Lighting change:
Sound idea:
No:
```

## Prompt Rules

- One keyframe prompt should describe one frame, not the entire ad.
- One keyframe should have one visual subject, one decisive action, one emotional state, and one product role.
- If the frame needs "and then", split it.
- If the prompt uses commas to list multiple sequential actions, split it.
- Each frame should have a clear narrative job and decisive visual moment.
- Keep product geometry consistent across frames.
- Avoid text generation inside images unless the user provides exact logo/pack assets and the tool can preserve them.
- Reserve negative constraints for actual failure modes: wrong packaging, extra labels, deformed hands, text artifacts, inconsistent face, product shape drift.
- For surreal ads, keep at least one realistic anchor in every frame: real product, real hand, real kitchen, real street, real pack shot.
- Do not use the same shot size and angle across all frames; vary scale and perspective to show discovery, mechanism, escalation, and resolution.
- Use match cuts and cause-effect transitions to connect product action with world-rule consequence.

## Storyboard Density

For director storyboard / shot list, use:

- 6-10 shots for 15s, usually 1.5-3s per shot.
- 12-18 shots for 30s, usually 1.5-3s per shot.
- 24-36 shots for 60s, usually 1.5-4s per shot.
- 32-48 shots for 75-90s, usually 1.5-4s per shot.

Do not output 6-second storyboard rows when the user is asking for 分镜, storyboard images, AI prompts, or video-generation planning. A 6-second range belongs only in a high-level script beat outline unless explicitly justified as a long take.

For AI keyframe generation, use:

- 8-12 keyframes for 15s.
- 16-24 keyframes for 30s.
- 28-40 keyframes for 60s.
- 36-54 keyframes for 75-90s.

Do not make every keyframe equally important. Mark:

- **Hero keyframe**: must be generated with high fidelity.
- **Continuity keyframe**: locks character/product/location consistency.
- **Transition keyframe**: supports video motion or edit logic.
- **End-frame keyframe**: pack/logo/brand composition.

If the user only asks for a compact script, keep the director storyboard concise. If the user asks for image generation, prompts, 分镜生图, storyboard images, or AI keyframes, output the expanded AI keyframe package.

## Keyframe Complexity Budget

Each AI keyframe prompt should fit this budget:

- 1 location
- 1 primary subject
- 1 secondary subject maximum
- 1 product placement
- 1 decisive action or pose
- 1 emotional state
- 1 shot size and angle
- 1 lighting setup
- 1 transition note, only if needed

Avoid:

- Multiple actions in one prompt.
- Multiple time states in one image.
- "Before and after" in one image.
- Several product placements in one frame.
- Explaining the whole concept inside every prompt.

## End Frame Requirements

Every ad script should have an end frame:

- Product or pack hero.
- Clear brand/logo area.
- One visual echo from the story.
- Optional slogan/CTA placeholder.
- Simple enough to become a poster.
