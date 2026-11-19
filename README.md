# VideoZero for Claude

Make animated videos without leaving Claude Code: product demos and launch videos for what you just built, explainers, kinetic typography, animated charts and diagrams, LaTeX, algorithm walkthroughs, 3D scenes, maps and social clips.

Claude writes the scenes as code; [VideoZero](https://videozero.ai) builds and checks them, shows Claude the frames so it can fix what looks wrong, gives you a link to watch the result, and exports MP4.

## Install

From the Claude plugin directory (once listed):

```
/plugin install videozero@claude-plugins-official
```

Or straight from this repository:

```
/plugin marketplace add VideoZero/claude-plugin
/plugin install videozero@videozero
```

On first use Claude Code opens your browser to sign in to VideoZero (a free account works). If that doesn't happen, run `/mcp`, pick `videozero` and authenticate.

## Use

Ask for a video in plain words, or use the command:

```
/videozero:make-video a 30-second launch video for the feature in this repo, 16:9
```

Claude reads your code for real names and screenshots, builds the video scene by scene, checks the frames, and replies with a link to watch it. Ask for changes in the same conversation; ask for an MP4 when you're happy.

## What's included

- **MCP server** — `https://engine.videozero.ai/mcp`: projects, scene builds, preview frames, components, icons, stock media, uploads and export.
- **Skill `make-video`** — how to work with VideoZero from a terminal: author scenes directly, check frames before reporting, share the link, upload local files and download exports.

## Pricing

Building and previewing videos is free. Exports, AI-generated images, narration, sound effects and music use credits; the free plan includes some. See [videozero.ai](https://videozero.ai) for plans.

## Support

Open an issue in this repository or write through [videozero.ai](https://videozero.ai). Privacy policy: [videozero.ai/privacy](https://videozero.ai/privacy). License: Apache-2.0.
