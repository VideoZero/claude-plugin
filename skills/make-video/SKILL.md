---
name: make-video
description: Make or edit an animated video with VideoZero — explainers, product demos, launch or feature videos, kinetic typography, animated charts and diagrams, LaTeX, algorithm walkthroughs, 3D scenes, maps, social clips, loops. Use when the user asks for a video, animation or motion graphics, wants to show off something they built, or wants to change, preview or export a VideoZero project.
argument-hint: "[what the video should show]"
---

# Making videos with VideoZero

VideoZero turns scene code you write into videos. The `videozero` MCP server (installed with this plugin) holds the projects, builds and checks every scene, renders preview frames you can look at, and exports MP4. Building is free; exports, AI images, narration, sound and music cost credits.

Request: $ARGUMENTS

## Start

1. Call `get_started` once per session, before anything else. Its result is the real manual: the authoring loop, which docs to read (`skills_read`), the user's plan and credits, and their recent projects. Follow it; this skill only adds what's specific to a terminal.
2. On the first call, Claude Code asks the user to sign in to VideoZero in the browser. If the tools fail with an auth error, tell the user to run `/mcp`, choose `videozero` and authenticate.

## Write the video yourself

Author scenes directly with `project_create`, `scene_update_build` and `scene_patch_build`. Don't call `video_generate` or `video_revise` unless the user explicitly asks for VideoZero to generate it for them: they spend credits and take the work out of your hands.

When the video is about the code in this repo, read the repo first (README, the feature's source, screenshots) and use real names, numbers and UI from it rather than placeholders. To use a local image or screen recording, call `asset_request_upload` and POST the file yourself:

```bash
curl -sS -F "file=@path/to/screenshot.png" "<upload_url from the tool>"
```

## Look before you report

You can't watch the video here, but you can see frames: check every scene with `scene_view_contact_sheet` and `scene_view_frames` (mid-animation as well as settled) and fix what looks wrong before telling the user it's done.

## Hand it over

The terminal can't play video. End every reply that changed the video with the project link: call `project_view` (it returns the link to put in your reply on hosts without a player) or `project_video_url`. Keep the reply short: what you made, the link, and anything you'd still improve.

When the user wants a file, call `project_export` (it costs credits, so mention that before the first one), then poll `project_export_get` until it returns the download link. To save it locally:

```bash
curl -L -o video.mp4 "<download_url>"
```
