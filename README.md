**Languages:** English | [简体中文](README.zh-CN.md)

# image-skills

Remove image backgrounds to transparent PNG, resize and compress app assets, and convert sprite sheets to aligned GIFs for **Claude Code** and **Codex** — generate the picture with your image tool, then finish the asset here.

This is a skill (not a hosted API). It does not redistribute Codex’s bundled imagegen skill. Cutout, resize, sprite-sheet split, and GIF encoding are deterministic image processing.

**Maintained successor to [image-assets-skill](https://github.com/x0c/image-assets-skill).** The skill is still named `image-assets` and lives in `image-assets/`. The old repository is an archived landing page.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![skills.sh](https://skills.sh/b/x0c/image-skills)](https://skills.sh/x0c/image-skills)

## What it does

- **Remove background → transparent PNG** (solid-color keying, or model cutouts)
- **Resize, compress, convert** PNG / WebP / AVIF / JPEG
- **Sprite sheet → aligned animated GIF** (N-grid split, feet-anchor, ping-pong)
- **App icon size sets** from one source image

Ask the assistant to process an image after install, or read the [full commands](image-assets/README.md).

```sh
python3 image-assets/scripts/image_assets_cli.py app-transparent \
  --input ./photos --output ./cutouts
```

## Install

Requires Node.js (for the `skills` CLI) and Python 3 (for the image processing helpers):

```sh
npx skills add x0c/image-skills -g
```

This installs the `image-assets` skill to every detected agent host. Restart your assistant.

If you use agentsync, maintain its canonical skill source instead of replacing shared tool-side links.

## Usage and dependencies

Solid-color frame processing needs Python; compression/conversion also needs Node.js; model cutouts install large local model dependencies on first use. **RMBG-2.0** is free for non-commercial use only (commercial use needs a BRIA license); **BiRefNet** is free including commercial use. Never upload access tokens.

Skill execution instructions are currently primarily in Chinese.

## Feedback and license

Report problems in this repository’s [Issues](https://github.com/x0c/image-skills/issues), with redacted errors and a minimal example.

[MIT](LICENSE); model licenses apply separately.
