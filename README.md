# reverse_and_rebuild

Understand a public app or shipped binary, then rebuild its core features as your own version, with a clean room evidence wall between understanding and building.

Merged for Muse from two MIT licensed sources. See `reverse_and_rebuild/SOURCE.md` for full attribution. See `DISCLAIMER.md` for the full disclaimer in Chinese and English.

---

## 中文说明

### 这是什么

这是一个给 Muse 用的技能：先看懂一个公开应用或已发布软件，再把它核心功能重做成你自己的版本。理解和重做之间有一道证据墙，只有行为说明能过去，反编译代码和原版素材过不去。

### 三种模式

- 只看懂：学一个目标是怎么做的，写完证据清单就停。
- 看懂并重做：从理解到上线走完整链路。
- 已有 recon 直接重做：已经有好的侦察图时，跳过理解阶段。

### 证据墙

只有这些能从理解阶段进入重做阶段：`replica/recon.md`、`replica/features.csv`、`replica/evidence.md`。

反编译代码、原版字符串、图片、图标、logo、商标、文案，一律不能进入克隆。

### 在 Muse 里怎么用

把 `reverse_and_rebuild` 文件夹复制到你的 Muse 自定义技能文件夹，然后直接说“逆向某某”或“克隆某某”。技能会先问目标、只做哪一环、重做版给谁用。

### 里面有什么

- `reverse_and_rebuild/SKILL.md`：合并后的工作流。
- `reverse_and_rebuild/skill.yaml`：技能描述文件。
- `reverse_and_rebuild/scripts/`：6 个标准库 Python 工具，做对比度、布局 diff、功能对齐、差评排序、品牌清扫、上架检查。
- `reverse_and_rebuild/references/`：侦察图、架构、测试计划、bug 报告、上线检查的模板。
- `reverse_and_rebuild/SOURCE.md`：来源说明。
- `reverse_and_rebuild/LICENSE-MIT-ORIGINAL-REPLICA` 和 `LICENSE-MIT-ORIGINAL-LEANREA`：两个原项目的 MIT 授权。

### 限制

- 只分析你拥有或有权分析的软件。
- 不做游戏外挂，不绕反作弊，不绕登录、付费墙、DRM 和授权检查。
- 账号、域名、密码、银行卡、密钥，永远是你自己动手。
- 技能里注明：这台 VM 不默认能用 Docker，Mac 专属命令只标 Mac，Linux 上缺的工具行标缺失用 fallback。

### 免责声明（简版）

本技能仅供学习、研究和在合法授权下的个人使用。使用者要自己遵守当地法律、软件授权和游戏服务条款。重做版必须换品牌，不得使用原版商标、logo 和文案。本项目不提供任何担保，也不是法律建议。完整版见 `DISCLAIMER.md`。

---

## English

### What this is

A skill for Muse: understand a public app or shipped binary, then rebuild its core features as your own version. An evidence wall sits between understanding and building. Only behavior specs cross it. Decompiled code and original assets do not.

### Modes

- Understand only: learn how a target works and stop after the evidence ledger.
- Understand and rebuild: run the full chain from understanding to deploy.
- Rebuild from an existing recon map: skip understanding when a good recon map already exists.

### Evidence wall

Only these may cross from understanding to building: `replica/recon.md`, `replica/features.csv`, and `replica/evidence.md`.

Decompiled code, original strings, images, icons, logos, trademarks, and copy must not enter the clone.

### Use in Muse

Copy the `reverse_and_rebuild` folder into your Muse custom skills folder, then ask Muse to understand or clone an app. The skill will ask for the target, the slice, and who the rebuilt version is for.

### What is inside

- `reverse_and_rebuild/SKILL.md`: the merged workflow.
- `reverse_and_rebuild/skill.yaml`: the skill descriptor.
- `reverse_and_rebuild/scripts/`: six standard library Python tools for contrast, layout diff, parity, review ranking, brand sweep, and listing lint.
- `reverse_and_rebuild/references/`: templates for recon, architecture, test plans, bug reports, and deploy preflight.
- `reverse_and_rebuild/SOURCE.md`: source attribution.
- `reverse_and_rebuild/LICENSE-MIT-ORIGINAL-REPLICA` and `LICENSE-MIT-ORIGINAL-LEANREA`: the original MIT licenses.

### Limits

- Analyze only software you own or have a right to analyze.
- Never use this skill to build a cheat, bypass an anti-cheat system, bypass a login or paywall or DRM, or exploit a kernel or driver flaw.
- Accounts, domains, passwords, cards, and live keys are always the user's own manual steps.
- This VM note from the skill: Docker is not assumed, macOS only rows are marked as Mac only, and rows for tools missing on a Linux VM are marked as missing there.

### Disclaimer (short version)

This skill is for learning, research, and personal use under lawful authorization only. Users must comply with local laws, software licenses, and game service terms on their own. A rebuilt version must be rebranded and must not use the original trademarks, logos, or copy. This project provides no warranty and is not legal advice. See `DISCLAIMER.md` for the full version.
