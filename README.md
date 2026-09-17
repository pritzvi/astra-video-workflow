# Astra Video Workflow

Turn a reference video into an editable ad: let Codex inspect the footage, plan the jobs, generate the performances through your connected tools, and build precise screens, captions and graphics locally.

**[Open the motion library](https://pritzvi.github.io/astra-video-workflow/) · [Download this kit](https://github.com/pritzvi/astra-video-workflow/archive/refs/heads/main.zip) · [Set up the tools](guides/setup.md)**

## Start here

1. Download the kit and open its folder in [Codex / the desktop app](https://developers.openai.com/codex/app/).
2. Follow [setup](guides/setup.md): connect OpenArt, install the included skills, then add Remotion and Blender when your edit needs them.
3. Put your own reference video and product images in a separate working project. Fill in the [brief](skills/video-analyzer/templates/ad-brief.md).
4. Paste the [starter request](prompts/start-here.txt). Codex makes a shot breakdown, a reference map and a priced generation plan before spending credits.
5. Approve one bounded batch. Review those outputs, then assemble and fix individual layers.

You can ask Codex to do the setup steps for you. A skill is a folder of instructions; installing it does not install the apps or buy model access. The model names available in your Codex account may differ from those shown in the tutorial.

## What each tool does

| Tool | Job | Get it |
|---|---|---|
| Codex | Research, plan, write prompts and editing code, inspect the result | [Desktop app download](https://developers.openai.com/codex/app/) |
| OpenArt MCP | Connect the agent to OpenArt's available video models | [Official setup](https://openart.ai/mcp/) · [Connection guide](guides/openart-mcp.md) |
| Video Analyzer skill | Break the reference into jobs and check each layer | [Included skill](skills/video-analyzer/SKILL.md) |
| Remotion | Exact app screens, captions, camera moves and motion graphics | [Official skills](https://github.com/remotion-dev/skills) · [Setup](guides/remotion.md) |
| Blender | Fit a replacement screen into moving footage and preserve foreground objects | [Download](https://www.blender.org/download/) · [Our editing skill](skills/blender-video-editing/SKILL.md) · [Setup](guides/blender.md) |
| FFmpeg | Inspect media, prepare source ranges and assemble outputs | [Download](https://ffmpeg.org/download.html) |

The Blender skill is original guidance from this project, **not an official Blender skill or a Blender MCP server**. Remotion's official skills are linked, not redistributed. **OpenArt officially lists Seedance 2.5, 2.0 and 2.0 Mini through its MCP.** The [connection guide](guides/openart-mcp.md) covers OAuth setup and checking the exact model inputs and price in your account. This release verified the endpoint’s authentication challenge; it did not authenticate an account or test a generation.

## Learn the workflow

- [Break down a reference and finish the edit](guides/workflow.md)
- [Split the work between agents](guides/parallel-editing.md)
- [Write Seedance prompts with clear reference roles](guides/seedance-prompting.md)
- [Language-app example](examples/language-app.md) and [boxing example](examples/boxing.md)
- [Character-sheet prompt](prompts/character-sheet.txt)
- [Twelve motion examples with copyable prompts](https://pritzvi.github.io/astra-video-workflow/)
- [Official source links](references/tool-links.md)

These resources describe an editing method. The download does not contain the tutorial's private portraits, voice recordings, provider receipts, copyrighted reference clips or finished ads. Use your own assets. The historical tutorial generations used a different provider; this kit's intended generation connection is OpenArt. Follow the live tool schema rather than copying a provider-specific request from the video.

Local editing avoids an additional video-generation charge for that edit. Your subscriptions, local computer time, software licensing and model calls still have their own costs. There is no guaranteed saving or fixed price per ad.
