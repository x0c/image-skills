# AGENTS.md

## 仓库布局与权威源指向

- 本仓库统一管理自维护的图像相关 Skill；当前发布 `image-assets/`（`SKILL.md` + `references/` + `scripts/` + `tests/` + `agents/openai.yaml` 是 Skill 内容，`image-assets/LICENSE` 为其许可）。
- 仓库级发布配套：根 `README.md` / `README.zh-CN.md` / `LICENSE`，以及 `.image-assets-sync.json`（skill 文件的哈希清单，发布时校验同步状态）。
- 本仓库是公开发布副本；维护者的本地权威源在私有同步目录中，对外只看本仓库与修复 PR/直接提交。

## 硬约束

- **身份**：所有 commit 用 `x0c <x0c@users.noreply.github.com>`（author 与 committer 同设置），不得出现真实姓名邮箱。
- **隐私**：禁止出现公司/组织名、内网地址、真实域名、个人标识、手机号（推送前敏感词扫描）。
- **语言**：Skill 正文（`SKILL.md` / `references/` / `scripts/`）用英文；README 中英双语（英文在前）。
- **验证**：改 `scripts/` 后跑 `python3 tests/test_grid_gif.py`；涉及真实图像处理的改动，至少用一张真实素材跑一次对应脚本冒烟；`.image-assets-sync.json` 的哈希与发布内容同步更新。

## 文档导航

| 文档 | 何时读 |
|---|---|
| `image-assets/SKILL.md` | 做抠图、改尺寸压缩、精灵图拆分、GIF 编码等图像资产处理时必读 |
| `image-assets/references/sprite-sheet-gif.md` | 精灵图转 GIF 时对照流程与坑 |
| `image-assets/references/environment.md` | 排查图像处理运行环境与依赖时 |
| `image-assets/references/apple-native-assets.md` | 处理 Apple 平台资产规格时 |
