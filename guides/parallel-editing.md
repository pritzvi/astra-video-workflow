# Give each agent one clear job

The lead agent keeps the brief, budget and final timeline. Workers get a small set of inputs, one output directory and concrete checks. This is useful when the UI can be built while a performance clip is being generated. If your client has no subagents, run the same assignments sequentially.

## Agree on the shared contract first

Write down output dimensions, frame rate, total duration, shot IDs, dialogue, palette, fonts and audio policy. For every source range, use either presentation timestamps or explicit frame numbers with its source frame rate. Use exclusive end frames in the edit list, so `[0, 90)` contains 90 frames.

| Owner | Inputs | Output and ownership | Depends on | Done means |
|---|---|---|---|---|
| Analyst / lead | Brief and full references | `plan/`; shared timeline and budget | Source access | Cuts, speakers, preservation map and priced batch reviewed |
| Performance worker | Approved job and reference map | `generation/actor/`; raw and selected takes | Batch authorization | Entire take inspected; prompt, job ID, cost and selection saved |
| UI worker | Product screenshots and screen timings | `work/ui/`; flat UI render and source | Agreed output contract | Correct states/text/timing; silent unless explicitly assigned audio |
| Screen worker | Original phone shots and flat UI | `work/screens/`; tracks, masks, composite | UI + source corners | No slipping edges; original foreground preserved |
| Graphics worker | Exact copy, palette, timings | `work/graphics/`; separate layers and source | Agreed output contract | Readable at delivery size; animation proves the narration |
| Assembly owner | Selected outputs and edit list | `work/assembly/`, `exports/` | Required assets | One consistent timeline, natural sound, complete playback |
| Reviewer | Render and source evidence | `review/` notes only | Review export | Reports timestamped defects; does not silently overwrite the cut |

Avoid two workers editing the same Remotion root, manifest or master file. Let workers register proposed changes in their handoff; the lead merges the shared timeline. Expensive retries should not race across workers: one job owner recovers pending job status and spends within the common cap.

## Copy this assignment

> Own `work/ui/` only. Read `brief.md`, `plan/shots.csv` and `plan/reference-map.csv`. Build the app interaction from the supplied screenshots at 1080×1920, 30 fps, 120 frames. Follow the reply timings in the shot list. Deliver `ui-flat.mp4` without audio, editable source, a preview still and `handoff.md`. Report real blockers promptly. Do not modify the master timeline or submit generation jobs.

Adjust dimensions and timing to your project. A 120-frame example is not a required clip length.

Each handoff records: inputs used; exact output path; dimensions/frame rate/frame count; whether audio exists; intended in/out and timeline placement; render command; checks completed; defects; and whether it is ready for review or accepted. Use the [handoff template](../templates/agent-handoff.md).

If an upstream clip changes length, tell the assembly owner before rebuilding dependent layers. Keep unfinished work marked honestly: assigned, working, blocked, ready for review and accepted describe different states.
