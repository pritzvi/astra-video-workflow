# Set up your ad workspace

You only need to understand the roles: Codex is the agent, a skill tells it how to work, an MCP connection exposes external tools, and Remotion/Blender make local edits.

## 1. Open Codex

Get the app from [OpenAI's desktop app guide](https://developers.openai.com/codex/app/). The current download page may use ChatGPT branding; this tutorial refers to the Codex workspace. Open a new project folder. Use a model available in your account; this kit does not require a particular preview model name. Keep the downloaded kit nearby so you can point Codex to it.

## 2. Add the two included skills

The easiest request is:

> Install `skills/video-analyzer` and `skills/blender-video-editing` from this downloaded kit as project skills. Copy their whole folders, including references and templates, into `.agents/skills/`. Keep existing skills. Confirm that you can read both SKILL.md files.

Or run these commands **from the downloaded kit folder**, replacing `../my-ad` with your project path:

```bash
mkdir -p ../my-ad/.agents/skills
cp -R skills/video-analyzer ../my-ad/.agents/skills/
cp -R skills/blender-video-editing ../my-ad/.agents/skills/
```

If either destination already exists, compare versions first. Open the target project in Codex and mention `$video-analyzer`. You can also point the agent directly at the skill file if automatic discovery is unavailable. See [Codex skills documentation](https://developers.openai.com/codex/skills/).

## 3. Connect generation

Follow [OpenArt MCP setup](openart-mcp.md). Ask Codex to inspect the connected tools without submitting a job. Confirm model, input types, duration, audio controls, price and account access before approving a generation. Install or connect the tools exposed by your account; a successful login page is not a successful generation test.

## 4. Add local editing tools

- [Remotion setup](remotion.md): install Node.js, create an editing project, and install the official agent skills.
- [Blender setup](blender.md): install Blender and verify its executable. No third-party Blender MCP is required for the included workflow.
- [FFmpeg](https://ffmpeg.org/download.html): install a build for your operating system. `ffmpeg -version` and `ffprobe -version` should both work in your terminal.

Ask Codex to report each installed version and run a tiny local render before starting the real edit. The setup checks should not call a paid video model.

## 5. Make a separate production folder

```text
my-ad/
  .agents/skills/
  brief.md
  inputs/              your private reference files, never overwritten
  plan/                shot list, reference map, budget
  generation/          exact requests, receipts and raw outputs
  work/                editable Remotion and Blender projects
  review/              previews and review notes
  exports/             selected final files
```

Copy the [brief template](../skills/video-analyzer/templates/ad-brief.md) to `brief.md`, add your files to `inputs/`, then use the [starter request](../prompts/start-here.txt). Planning and local editing can proceed while an account connection is being resolved; paid generation waits for the agreed batch approval.
