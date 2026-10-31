**语言：** [English](README.md) | 简体中文

# image-skills

为 **Claude Code** 和 **Codex** 抠图成透明 PNG、缩放压缩应用素材、把精灵表转成对齐的 GIF——用你的生图工具出图，再在这里做可交付资产。

这是技能，不是在线抠图服务。不分发 Codex 内置 imagegen。抠图、缩放、切帧和 GIF 编码都是确定性图像处理。

**这是 [image-assets-skill](https://github.com/x0c/image-assets-skill) 的后续维护仓库。** 技能名称仍为 `image-assets`，位于 `image-assets/`。旧仓库仅作归档入口。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![skills.sh](https://skills.sh/b/x0c/image-skills)](https://skills.sh/x0c/image-skills)

## 能做什么

- **抠图 → 透明 PNG**（纯色键控，或模型分割）
- **缩放、压缩、转码** PNG / WebP / AVIF / JPEG
- **精灵表 → 对齐的动画 GIF**（N 宫格切帧、脚部锚点、往返播放）
- **应用图标多尺寸** 从一张源图导出

装好后请助手处理图片，或阅读 [完整命令](image-assets/README.md)。

```sh
python3 image-assets/scripts/image_assets_cli.py app-transparent \
  --input ./photos --output ./cutouts
```

## 安装

需要 Node.js（装 `skills` CLI 用）和 Python 3（跑图像处理辅助脚本用）：

```sh
npx skills add x0c/image-skills -g
```

一次把 `image-assets` 技能装到所有已识别的编程助手。新开会话（或重启 agent）以加载技能。

使用 [agentsync](https://github.com/x0c/agentsync) 的用户应维护统一技能源，不要复制覆盖工具侧的共享链接。

## 🧩 AI 编程工具链里的相关工具

如果你每天在多个 AI 编程助手之间切换，看看这套本地优先工具链的其余部分：

| 仓库 | 说明 |
| :--- | :--- |
| **[corral](https://github.com/corral-dev/corral)** | 在终端会话管理器里并排跑 Claude Code、Codex、OpenCode、Cursor 和 Pi，再从 iPhone 或 Mac 上继续。 |
| **[subswap](https://github.com/x0c/subswap)** | 查剩余额度，一键切换 Claude Code、Codex、Cursor、Kimi Code 和 OpenCode 的账号，不用反复登录。 |
| **[agentsync](https://github.com/x0c/agentsync)** | 以一份本地源统一同步 `AGENTS.md`、`CLAUDE.md`、skills 和 MCP 配置到各编程助手。 |
| **[agent-doc-skills](https://github.com/x0c/agent-doc-skills)** | 可导航的项目知识库 skills（`doc-init`、`doc-update`、`doc-compact`），让 coding agent 不再每个会话都重新认识你的仓库。 |

## 用法和依赖

纯色切帧需要 Python；压缩转换额外需要 Node.js；AI 抠图模型会在首次运行时下载本地权重。**RMBG-2.0** 免费仅限非商业（商用需向 BRIA 购买授权）；**BiRefNet** 完全开放，含商用。不要上传访问令牌。

注：内部技能提示词（`SKILL.md`）目前为中文。

## 反馈与许可证

请在本仓库 [Issues](https://github.com/x0c/image-skills/issues) 反馈，附脱敏后的错误和最小样例。

[MIT](LICENSE)；模型许可独立适用。
