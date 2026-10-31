**Languages:** English | [简体中文](README.zh-CN.md)

# image-skills

Remove image backgrounds to transparent PNG, resize and compress app assets, and convert sprite sheets to aligned GIFs for **Claude Code** and **Codex** — generate the raw image with your favorite model, then turn it into a production-ready asset here.

This is a skill (not a hosted API). It does not redistribute Codex’s bundled imagegen skill. Cutout, resize, sprite-sheet split, and GIF encoding are deterministic image processing.

**Maintained successor to [image-assets-skill](https://github.com/x0c/image-assets-skill).** The skill is still named `image-assets` and lives in `image-assets/`. The old repository is an archived landing page.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![skills.sh](https://skills.sh/b/x0c/image-skills)](https://skills.sh/x0c/image-skills)

## What it does

- **Remove background → transparent PNG** (solid-color keying or model-based cutout)
- **Resize, compress, convert** PNG / WebP / AVIF / JPEG
- **Sprite sheet → aligned animated GIF** (N-grid split, feet-anchored, ping-pong)
- **App icon sets** from one source image

Ask the assistant to process an image after install, or see the [full commands](image-assets/README.md).

```sh
python3 image-assets/scripts/image_assets_cli.py app-transparent \
  --input ./photos --output ./cutouts
```

## Install

Requires Node.js (for the `skills` CLI) and Python 3 (for the image processing helpers):

```sh
npx skills add x0c/image-skills -g
```

This installs the `image-assets` skill across all detected coding agents. Start a new session (or restart your agent) to load it.

If you use [agentsync](https://github.com/x0c/agentsync), maintain its canonical skill source instead of replacing shared tool-side links.

## 🧩 Related Tools in the AI Coding Suite

If you run multiple AI coding agents daily, check out the rest of the local-first toolkit:

| Repository | Description |
| :--- | :--- |
| **[corral](https://github.com/corral-dev/corral)** | Run Claude Code, Codex, OpenCode, Cursor & Pi side-by-side in a terminal session manager, then continue from iPhone or Mac. |
| **[subswap](https://github.com/x0c/subswap)** | Check remaining quota and switch Claude Code, Codex, Cursor, Kimi Code & OpenCode accounts without logging out. |
| **[agentsync](https://github.com/x0c/agentsync)** | Sync `AGENTS.md`, `CLAUDE.md`, skills, and MCP configs across coding agents from one local source of truth. |
| **[agent-doc-skills](https://github.com/x0c/agent-doc-skills)** | Navigable project knowledge base skills (`doc-init`, `doc-update`, `doc-compact`) so coding agents don't rediscover your repo every session. |

## Usage and dependencies

Solid-color frame processing needs Python; compression/conversion also needs Node.js; AI cutout models download their local weights on first run. **RMBG-2.0** is free for non-commercial use only (commercial use needs a BRIA license); **BiRefNet** is free including commercial use. Never upload access tokens.

Note: The internal skill prompts (`SKILL.md`) are currently written in Chinese.

## Feedback and license

Report problems in this repository’s [Issues](https://github.com/x0c/image-skills/issues), with redacted errors and a minimal example.

[MIT](LICENSE); model licenses apply separately.
