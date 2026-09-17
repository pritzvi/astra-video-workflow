---
name: blender-video-editing
description: Use local Blender for filmed-screen replacement and layered video compositing when exact UI, original camera motion, foreground objects and sound must be preserved.
---

# Blender video editing

This is an original project skill, not an official Blender skill or MCP package. Use the installed Blender executable and its Python interface, checking its version first. Read [references/screen-composite.md](references/screen-composite.md) when replacing a filmed display.

## Workflow

1. Inspect the actual source and desired change. Preserve the original file, audio and approved edit. Identify continuous shots and their source timestamps.
2. Agree on the exact display aperture, UI state timing, output frame rate/size and foreground objects. Keep the flat UI independent from the moving camera.
3. Make a local proof on the hardest motion/occlusion interval. Show tracked corners, mask and composite at matching timestamps. Do not claim success from a single still.
4. Once the approach works, apply it per shot, with no interpolation through cuts. Keep geometry, masks, captions and audio as separate assets.
5. Deliver a new `.blend` file, any scripts and tracks, rendered output, command/version notes and a source-to-output mapping. Check the complete composite at native playback and difficult frames at delivery resolution.

For automation, use the current Blender Python API rather than guessing node names from another version. Run scripts with `--python-exit-code 1` so failures do not look like success. Render a few frames before a full sequence. Use paths relative to the private working project where practical; do not overwrite source inputs or require a paid model for a local geometry fix.

Leave original picture outside the changed display/necessary masks intact. Keep native audio at natural speed and use identical picture/audio edits unless the user requests a different method. A separately authored graphic can be composited above footage; do not confuse that with requesting unwanted text from a video generator.
