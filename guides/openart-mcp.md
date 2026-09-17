# Connect OpenArt to Codex

OpenArt's [official MCP page](https://openart.ai/mcp/) lists Seedance **2.5, 2.0 and 2.0 Mini** alongside other image/video models. Its remote server is `https://mcp.openart.ai/mcp`, using Streamable HTTP and browser OAuth. No API key is needed for this route; you sign in with your OpenArt account.

**Release check — September 17, 2026:** unauthenticated initialization and tool discovery reached the server and returned the expected OAuth challenge. The authorization metadata identifies OpenArt. We did not connect an account, inspect its private model forms or generate a video. Your exact reference inputs, output settings, price and model access must be checked after sign-in.

## 1. Add the connection

With the [Codex CLI](https://developers.openai.com/codex/cli/) installed, run:

```bash
codex mcp add openart --url https://mcp.openart.ai/mcp
codex mcp login openart
```

The second command opens the account authorization flow. Sign in yourself and review the requested permissions. Do not paste passwords or tokens into chat. If an `openart` entry already exists, inspect it first rather than adding a duplicate.

If you prefer the desktop settings, add an MCP server named `openart`, choose the remote/Streamable HTTP option, and enter that same URL. Use the offered account sign-in. Exact labels vary with app version; [Codex's MCP documentation](https://developers.openai.com/codex/mcp/) describes the supported settings and OAuth commands. Use one setup method.

Check that the connection is present:

```bash
codex mcp list
```

A connected server is not proof that a particular generation request is supported. Open the project in Codex and do the read-only capability check next.

## 2. Check the selected model without spending

Paste this into the agent:

> Inspect the connected OpenArt tools without generating or uploading anything. List the available Seedance versions and modes. Read the actual model input form for the version we intend to use: image, video and audio references; each reference's limits and role; native audio; duration; resolution; aspect ratio; upload requirements; and how to check a job and retrieve its result. Check account access and obtain a price estimate if the tools support one. Report fields or pricing you cannot verify. Do not submit a paid request yet.

Save the result in the [capability template](../skills/video-analyzer/templates/capabilities.md). OpenArt's product pages describe model capabilities, but a model-wide limit is not a promise that every MCP mode exposes it. Use the discovered schema, not a copied request from another provider. If the desired video/audio reference field is missing, report that specific limitation and adjust the plan before paying.

## 3. Approve one small batch

Use your own reference files. Have the agent show the exact model, prompt, ordered reference roles, output settings, expected cost and acceptance checks. Approve the planned batch within your existing credits. Keep the job receipt, retrieve the output, and inspect picture and sound before expanding. Do not buy credits automatically or duplicate a job while its submission status is uncertain.

## Optional: OpenArt CLI

OpenArt also publishes an [official CLI](https://github.com/OpenArt-AI/cli), linked from its MCP page. Its documentation covers `openart login`, model discovery, `model form`, cost estimates and creation status/downloads. It can be convenient in Codex, but you do not need both connections to follow this kit. Follow its current installation guide if you choose it; no CLI was installed by this release.

The tutorial's existing example generations retain their original provider history. Naming OpenArt as the route for your new project does not mean those historical jobs were submitted through OpenArt.
