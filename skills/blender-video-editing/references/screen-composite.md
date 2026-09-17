# A screen replacement that survives movement

## Inputs and geometry

Prepare the original continuous phone shot, flat replacement UI, exact source range, UI playback offset and original audio. Inspect whether the screen is planar enough for a four-corner mapping. Strong rolling shutter, curvature, reflections or occlusion may need additional treatment; a corner pin alone cannot solve every surface.

For each shot, measure the visible display aperture in source coordinates. Keep consistent corner ordering (top-left, top-right, bottom-right, bottom-left). Record coordinate origin, pixel dimensions and frame/timestamp for every sample. Pixel coordinates measured from the top-left need conversion if the chosen Blender node uses bottom-left normalized coordinates. Verify with a labeled test grid before using the app UI.

Use tracking or manual keyframes appropriate to the shot. Inspect the result between keyframes; abrupt movements can slip even when endpoints look right. Do not reuse a previous shot's track through an editorial cut.

## Layers, back to front

1. Original filmed plate.
2. Screen insert warped into the display aperture.
3. Relevant screen reflections, blur and lighting treatment.
4. Original hand, camera island, bezel or other foreground holdouts.
5. Editorial captions/graphics that genuinely belong above the screen.

Clip the insert to the display, not to the phone's outside edge. Masks should follow the actual foreground silhouette. A rectangular patch around captions can bring the old UI back. If captions are flattened into footage, inspect whether they can be isolated; reconstruct only when needed and acknowledge any loss of fidelity.

Keep app animation and photographed camera movement separate. The UI's internal animation happens once, and the corner transform attaches it to the moving phone. Do not add the plate's camera shake to the complete composite again.

## Color and motion

Render the UI sharply at a sensible source size, then match the insert to the photographed display's brightness, saturation, blur and motion. Preserve ordinary phone-camera texture. Check frame edges for seams. Use the Blender version's correct color-management settings and inspect the rendered result rather than assuming a preview transform is the export.

## Output and review

Keep an image-sequence or other suitable intermediate when frame-accurate compositing matters, then encode a review file. Reattach preserved audio with the same edit boundaries. Check the first/last frames, motion peaks, finger crossings, caption reveals and speech tails. Watch at natural speed to catch swimming corners and mask flicker.

The final handoff includes the `.blend` file, construction script if used, geometry/mask data, flat UI source, rendered sequence/video and command. State which intervals were inspected and any remaining defect. A render that exits successfully is not evidence that the screen is attached correctly.

Official references: [Blender manual](https://docs.blender.org/manual/en/latest/) and [Python API](https://docs.blender.org/api/current/). Read the page matching your installed version when a node or property differs.
