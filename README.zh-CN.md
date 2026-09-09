[English](README.md) | 简体中文

# image-skills

为 Claude Code 和 Codex 准备最终图像素材：抠图、透明 PNG、缩放、压缩、格式转换，以及精灵表切帧和 GIF 对齐。

**这是 image-assets-skill 的后续维护仓库。** 技能名称仍为 `image-assets`，位于本仓库的 `image-assets/` 子目录。旧仓库仅保留迁移入口。

## 安装

需要 Git 和 Python 3。在一个尚无 `image-skills` 文件夹的目录执行：

```sh
git clone https://github.com/x0c/image-skills.git
python3 -c "from pathlib import Path; import shutil; shutil.copytree('image-skills/image-assets', Path.home()/'.claude/skills/image-assets')"
```

Windows PowerShell 将 `python3` 换为 `py -3`。Codex 用户将命令中的 `.claude` 换为 `.codex`。重启助手。

安装遇到目标目录已存在时会停止，避免覆盖自己的修改。升级或从旧仓库迁移时，先备份现有 `image-assets` 文件夹并将其移出技能目录，再执行复制。使用 agentsync 的用户应维护统一技能源，不要复制覆盖工具侧的共享链接。

## 用法和依赖

安装后请助手处理图片，或阅读 [完整能力与命令](image-assets/README.md)。纯色切帧需要 Python；压缩转换额外需要 Node.js；模型抠图会安装较大的模型依赖。RMBG-2.0 有访问与商用授权限制，详见完整说明；不要上传访问令牌。

图像生成工具负责生成或编辑源素材，image-assets 负责后续确定性处理。本仓库不分发 Codex 内置 imagegen 技能。技能执行正文目前主要为中文。

## 反馈与许可证

请在[当前仓库 Issues](https://github.com/x0c/image-skills/issues)反馈，附脱敏后的错误和最小样例。

[MIT](LICENSE)；模型许可独立适用。
