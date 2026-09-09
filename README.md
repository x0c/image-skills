English | [简体中文](README.zh-CN.md)

# image-skills

Prepare final image assets for Claude Code and Codex: background removal, transparent PNGs, resizing, compression, format conversion, sprite-sheet splitting, and aligned GIF output.

**This is the maintained successor to image-assets-skill.** The skill is still named `image-assets` and lives in the `image-assets/` subdirectory. The old repository is retained as a migration landing page.

## Install

Requires Git and Python 3. Run in a directory without an existing `image-skills` folder:

```sh
git clone https://github.com/x0c/image-skills.git
python3 -c "from pathlib import Path; import shutil; shutil.copytree('image-skills/image-assets', Path.home()/'.claude/skills/image-assets')"
```

In Windows PowerShell, replace `python3` with `py -3`. For Codex, replace `.claude` with `.codex`. Restart your assistant.

Installation stops if the destination already exists, preserving local changes. To upgrade or migrate from the old repository, back up your existing `image-assets` folder and move it outside the skill directory before copying. If you use agentsync, maintain its canonical skill source instead of replacing shared tool-side links.

## Usage and dependencies

Ask your assistant to process an image, or read the [full capabilities and commands](image-assets/README.md). Solid-color frame processing requires Python; compression/conversion also needs Node.js; model cutouts install large model dependencies. RMBG-2.0 has access and commercial-license restrictions detailed in the full guide. Never upload access tokens.

Use an image-generation tool for source visuals, then image-assets for deterministic processing. This repository does not redistribute Codex's bundled imagegen skill. Skill execution instructions are currently primarily in Chinese.

## Feedback and license

Report problems in the [current repository's Issues](https://github.com/x0c/image-skills/issues), with redacted errors and a minimal example.

[MIT](LICENSE); model licenses apply separately.
