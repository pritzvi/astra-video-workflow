# Remotion: screens, captions and motion graphics

Remotion builds video with React code. In this workflow it draws exact app screens and graphics; it does not generate a human performance. Install its [official agent skills](https://www.remotion.dev/docs/ai/skills) so Codex can use the current conventions:

```bash
npx skills add remotion-dev/skills
```

Choose your agent and project when prompted. The official repository is [remotion-dev/skills](https://github.com/remotion-dev/skills). This kit links to it instead of repackaging its contents.

## Make a project

Install a supported [Node.js LTS release](https://nodejs.org/en/download), then check `node --version` and `npm --version`. From your production's `work/` folder, create a new project:

```bash
npx create-video@latest
```

Use the wizard to choose a new folder and template. Open that folder, install dependencies with `npm install`, and start its preview with `npm run dev`. Use the generated project's actual scripts. Current system requirements and scaffold options are in the [official installation guide](https://www.remotion.dev/docs).

Give Codex this first request:

> Use the official Remotion skills. Create a five-second silent screen interaction from my app screenshots at the agreed output size and frame rate. Show idle, user input and app reply as coherent states. Keep all text sharp and editable. Produce a preview still, then render the short sequence. Save the source and exact render command.

In Studio, use **Render**, or run `npx remotion render` and select the composition. The [rendering guide](https://www.remotion.dev/docs/render) covers output options. Confirm the short render works before building a long sequence.

## Hand it to the editor

Export a flat screen layer at its intended size and frame rate. Include the duration, which frame starts the reply, and whether audio is present. Blender can then fit the flat layer into a photographed phone. Captions, UI overlays and camera effects stay separate so text can remain sharp while the footage moves or blurs.

For reference-faithful screen demonstrations, compare the source at the same state and scale. A cursor should hover, click and trigger a visible result in that order. Say when a demonstration is reconstructed; a recreation must not imply a live authenticated job or invent tool output.

Local rendering has no Seedance generation charge. Check [Remotion's license and pricing](https://www.remotion.dev/license) for your own use.
