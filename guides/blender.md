# Blender: fit the screen into the shot

Use Blender when the ad already contains a moving phone or display and you need precise replacement pixels. Remotion makes the flat interface; Blender fits it into the filmed screen while keeping the surrounding footage.

The included [blender-video-editing skill](../skills/blender-video-editing/SKILL.md) is original project guidance. It is not maintained by Blender and is not an MCP server. Codex can write a Python script and run Blender locally; a third-party connector is optional.

## Install and check

Download Blender from [blender.org](https://www.blender.org/download/). Launch it once and confirm it runs. In a terminal, check:

```bash
blender --version
```

If Blender is not on your command path, use the executable's full path. The usual macOS application path is:

```bash
"/Applications/Blender.app/Contents/MacOS/Blender" --version
```

On Windows or Linux, use the location chosen by your installer. Ask Codex to find that installed executable rather than guessing a versioned folder.

Blender supports background scripts and rendering. For a script Codex has created and reviewed:

```bash
blender --background --python-exit-code 1 --python work/build_composite.py
blender --background work/phone-composite.blend --render-output //preview/frame_ --render-format PNG --render-frame 1
```

These are command patterns; `work/build_composite.py` and the `.blend` file are outputs the agent creates for **your** footage. Put rendering arguments after loading the file, and render last. See the [official command-line manual](https://docs.blender.org/manual/en/latest/advanced/command_line/arguments.html).

## First useful test

> Use `$blender-video-editing` to replace the display in the hardest two seconds of my phone shot with the flat Remotion UI. Preserve the original phone, hand, camera movement and audio. Show the four screen corners, the foreground mask, and the final composite at several frames. Save the script and Blender project. Make this local test before extending it across the full ad.

Choose the hardest two seconds because a still frame can hide slipping corners, blurry edges or a hand disappearing behind the insert. Once that interval works, reuse its method shot by shot. Different camera cuts require separate tracks.
