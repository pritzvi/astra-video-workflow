# Connect InVideo to your agent

**Verified September 17, 2026:** InVideo's public `https://mcp.invideo.io/sse` server connects and exposes one tool: `generate-video-from-script`. Its inputs are script, topic, vibe, target audience and platform. It currently exposes **no Seedance model selector or image/video/audio-reference inputs**. Connecting this public server alone therefore does not reproduce the tutorial's reference-driven Seedance workflow. Continue local planning and editing, and obtain an InVideo connection that explicitly supports the required controls before paid generation.

The [official InVideo MCP page](https://invideo.io/ai/mcp/) links a [help article](https://help.invideo.io/en/articles/11316042-invideo-model-context-protocol-server) whose indexed version documents that address. The article itself was unavailable during this release; we verified the server directly with initialization and tool discovery only. No video was generated, account connected or credits spent.

## Add the working connection to Codex

Install [Node.js](https://nodejs.org/en/download) first. Codex supports local STDIO servers and Streamable HTTP; this InVideo endpoint uses the older SSE transport. The community [mcp-remote bridge](https://github.com/punkpeye/mcp-remote) adapts it to STDIO. The bridge command below was tested for initialization and tool discovery with version `0.14.2`.

If the Codex CLI is installed, run:

```bash
codex mcp add invideo -- npx -y mcp-remote@0.14.2 https://mcp.invideo.io/sse --transport sse-only
codex mcp list
```

Or, in the desktop app, open **Settings → MCP servers → Add server**. Name it `invideo`, choose **STDIO**, set the command to `npx` and the arguments to:

```text
-y mcp-remote@0.14.2 https://mcp.invideo.io/sse --transport sse-only
```

Save, select **Restart**, and use `/mcp` to inspect connected servers. These controls and CLI syntax are documented in [Codex's MCP guide](https://developers.openai.com/codex/mcp/). Choose one installation method so you do not create duplicate entries. The community bridge is separate from InVideo and OpenAI. If first startup is slow while `npx` downloads it, retry server startup after that completes; do not submit a generation to test connectivity.

## Check what this connection can actually do

Once connected, give Codex this request:

> Inspect the InVideo MCP tools without generating anything. List the actual tools available, whether this account can select Seedance, the exact model version/mode, and whether image, video and audio references are accepted. Check native audio, duration, resolution, reference limits, upload method, job-status lookup and the price shown before submission. Report anything the connection cannot verify. Do not submit a test or spend credits yet.

Save the result in the [capability template](../skills/video-analyzer/templates/capabilities.md). If the connection only exposes a high-level video creator and cannot control the requested reference inputs, say so. Use an explicitly supported InVideo workflow or revise the plan with the user. A model being offered in InVideo's web interface does not prove that every MCP tool exposes it.

For context, InVideo's [Seedance 2.0 help page](https://help.invideo.io/en/articles/14755814-create-with-seedance-2-0) describes multimodal reference inputs and 4–15-second clips in its product interface. Those controls were not present in the public MCP schema checked above.

Before the first paid batch, show the exact inputs, spoken words, model settings and total cap. After submission, save the returned job ID and check that ID until it finishes. If a response times out, recover the existing job before submitting another. Keep credentials and expiring upload URLs private; share local asset names and reference roles in a public handoff.
