# Seedance prompting: one job for each reference

Choose the exact model and endpoint before writing the final request. **Seedance is the model family; OpenArt is the connection in this kit.** A different provider can expose different settings, accepted files, durations and billing for the same named model.

Use the current [OpenArt MCP model listing](https://openart.ai/mcp/) and [BytePlus prompting guide](https://docs.byteplus.com/en/docs/ModelArk/2607689) as source references. Confirm every limit against the actual connected tool. A Seedance 2.5 reference allowance must not be copied into a Seedance 2.0 request, and a model-wide capability is not proof that a particular provider exposes it. Record the date and schema in the [capability check](../skills/video-analyzer/templates/capabilities.md).

## Write the roles before the prose

| Asset | Role | What it must not accidentally control |
|---|---|---|
| Performance video | Pose, camera, pauses and reaction | Actor identity or unwanted embedded speech |
| Identity image(s) | Face, hair, clothing | A conflicting camera angle or stylized skin |
| Voice recording, when supported | Approved vocal identity and delivery | Music, room noise or another speaker |
| Product screenshot | UI appearance reference | A promise of exact readable generated text |

Use the reference labels the actual tool accepts. Do not invent special tokens such as `@video1` unless its documented schema uses them. Keep the original role map alongside the uploaded order.

## Performance prompt example

> Create a natural phone-camera shot of the adult character from the identity images. Use the performance clip for the low camera angle, glance down at the phone, short pause and amused reaction. Keep the room lighting and ordinary skin texture. He looks at the phone and says exactly: “Could you say that a little slower?” His free hand makes one small questioning gesture, then settles. New speech uses the supplied approved voice reference. Preserve the pause after the question. Clean footage with speech and quiet room tone only. No added captions, titles, logos or background music.

Only include the voice-reference sentence when the endpoint accepts and uses that input. Exact generated wording and absence of overlays still need review. Native audio being enabled does not prove that the requested voice was used.

## Action prompt example

> A tired adult boxer faces the heavy bag. Left jab, then a right cross makes clear contact. The bag recoils. His hands return to guard and he breathes before beginning again. Keep the camera planted at chest height with slight natural handheld movement. No spinning, orbiting camera, text or music.

Describe the visible cause and result—glove contacts, bag moves, guard returns—so you can judge whether it happened. Repair that action shot without discarding a good speaking take.

## Separate audio deliberately

An uploaded video may contain speech even when you provide no separate audio reference. If replacing its speaker and voice, prepare an actor-only excerpt and remove its embedded audio when appropriate. Preserve the original audio separately for any app replies or reactions that should remain. State exact new dialogue and each speaker's role. Do not mute the app's reply simply because the actor's voice changes.

## Keep continuity practical

Reuse the same approved identity and voice sources across jobs. An ending frame can guide the next pose; only a documented start-frame feature can enforce its own stated constraint. Watch the join: expression, gaze, hand position, light and room tone can change even with identical references. A cutaway or a clean editorial cut may be better than another long batch.

Make a short first batch, inspect the full result and record the defect before retrying. Keep the prompt focused on the failed behavior. A retry fixes a diagnosed creative or technical defect within the authorized cap; it is not a way to evade a provider's safety decision.

## Cost comparisons

Estimate output duration × verified rate, adding any provider charges for reference input, audio or minimum duration. Keep that estimate separate from actual receipts. If comparing a planned pass to ten assumed attempts, label the number of attempts as an assumption. A model/version change prevents a controlled workflow-only comparison.
