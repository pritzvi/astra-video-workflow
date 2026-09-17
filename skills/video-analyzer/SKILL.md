---
name: video-analyzer
description: Analyze reference videos for an ad, plan focused generation and local editing, and inspect the assembled result. Use when recreating or adapting a reference while preserving its performance, timing, screens or sound.
---

# Video Analyzer

Turn the user's reference into an editing plan with inspectable outputs. Preserve their intended changes and approved work. This folder is self-contained: keep `references/` and `templates/` when installing it.

Read [references/workflow.md](references/workflow.md) for the production procedure. Use [templates/ad-brief.md](templates/ad-brief.md) when essential intent is missing; infer routine choices from the user's request rather than asking them to fill every field.

## Decisions that matter

- Inspect the complete visual and audio source. A transcript cannot establish a gesture, angle or cut; sampled stills cannot establish continuous movement. State the actual inspection limits.
- Split work by what must change: performances for generation; exact interfaces and graphics for local editing; existing successful picture/audio for preservation. An app reply is a separate speaker even when it shares a file with the person.
- Give each reference one stated role. Identity, performance, voice and UI are different jobs. A reference with unwanted embedded speech can still condition a model's audio.
- For this kit, discover the connected InVideo tools first. Confirm exact model, mode, input types, audio behavior, duration and pricing from the actual tool/schema. The public website or a login screen does not prove account capability. If a required tool is unavailable, report the specific missing operation and continue independent analysis/local work.
- Present the priced first batch and wait for its approval before paid inference. Retain earlier authorization within its stated scope. For allowed retries, diagnose a real failure and stay within the cap. Never silently repurchase credits or duplicate an ambiguously submitted job.
- Keep native on-camera speech and picture at natural speed by default, with matching cuts. A requested voice replacement is a separate reviewed method; do not stretch whole spoken passages to fill generated picture.
- Rendered, inspected and accepted are separate states. Deliver source files, reproduction instructions and timestamped limitations alongside the export.

## Outputs

Create a brief, reference map, shot list, capability check, generation plan, receipt ledger, source-to-final edit list and review notes only as needed for the job. Templates are in `templates/`. Keep requests and original outputs in the user's private working project, not in this public kit. Do not place tokens or signed media URLs in shared summaries.

For Remotion use its installed official skill, if available. For filmed-screen compositing, use the companion `blender-video-editing` skill if installed, or inspect Blender's current manual and available local tools. Do not claim either dependency is installed merely because this skill mentions it.
