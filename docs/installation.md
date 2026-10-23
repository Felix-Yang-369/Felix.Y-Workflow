# Installation · 安装指南

[English README](../README.md) · [中文首页](../README.zh-CN.md)

Current package: **0.5.0**, with six callable Skills and all 13 original workflows preserved as editable modules. The repository is `Felix-Yang-369/Felix.Y-Workflow`; the marketplace and plugin IDs remain `felix-workflows`. The commands below require a Codex CLI that includes `codex plugin`.

## Install from GitHub

The repository is public. Install the Codex CLI, then run:

```sh
codex plugin marketplace add Felix-Yang-369/Felix.Y-Workflow
codex plugin add felix-workflows@felix-workflows
```

Start a new conversation and confirm that the plugin is available. Invoke one of the six domain Skills; installation does not cause every message to run every Skill.

```text
$knowledge-management
$finance-management
$schedule-management
$learning-management
$research-management
$creative-management
```

For example: `Use $knowledge-management to review this note and propose improvements.` The original 13 names now identify [complete reference modules](workflows.md); use the six entries above for invocation.

## Install editable local source

Clone the repository into a location you control, then register that local directory:

```sh
git clone https://github.com/Felix-Yang-369/Felix.Y-Workflow.git
cd Felix.Y-Workflow
codex plugin marketplace add .
codex plugin add felix-workflows@felix-workflows
```

Use `codex plugin marketplace list` to check which source directory is registered. Edit the source under `plugins/felix-workflows/`; reinstall after saving and verify in a new conversation. Old conversations may retain earlier instructions.

If this marketplace name is already registered from GitHub or another directory, first inspect its source and preserve edits made there. To intentionally switch to this checkout, remove only the marketplace registration and register the chosen directory:

```sh
codex plugin marketplace list
codex plugin marketplace remove felix-workflows
codex plugin marketplace add .
codex plugin add felix-workflows@felix-workflows --json
```

Use this sequence only when switching sources. The chosen local checkout is the maintained source; do not edit the generated installation cache. The plugin ID stays `felix-workflows@felix-workflows`.

## Update and use another computer

For a GitHub-backed marketplace:

```sh
codex plugin marketplace upgrade felix-workflows
codex plugin add felix-workflows@felix-workflows
```

For an editable local checkout, preserve and review local changes before pulling source updates. In that checkout:

```sh
git status --short
git diff
git pull --ff-only
codex plugin add felix-workflows@felix-workflows --json
```

Run the pull after reviewing and saving your edits; if Git reports conflicts or diverging history, keep both versions and resolve them before reinstalling. `marketplace upgrade` refreshes Git-backed marketplace snapshots, not a registered local checkout. Source changes and GitHub publication are separate from local installation.

On another computer, repeat installation and connect the services needed by your tasks. No invitation is required to read this public repository. Access to Notion, calendars, or other accounts is granted separately by their owner.

If similarly named standalone Skills or an older plugin are present, compare their complete files first. Preserve unique rules, confirm the plugin works, and back up any standalone copy before disabling it. Avoid duplicate entries.

## Verify the result

```sh
codex plugin list --marketplace felix-workflows --json
```

Check `version: "0.5.0"`, `installed: true`, and `enabled: true`, plus the expected source directory. Compare source and cache files when preserving local edits, then test a harmless workflow in a new conversation. File consistency, actual Skill behavior, and visual checks of changed business pages are separate forms of verification.

## 中文说明

当前公开版本为 **0.5.0**，包含六类入口、完整保留的 13 个原工作流模块和两份新增金融方法。安装命令见上方；仓库名为 `Felix.Y-Workflow`，插件与市场标识继续使用 `felix-workflows`。调用时使用上方六个 `$...-management` 入口，旧名用于查找模块。

需要自行编辑时，克隆到自己控制的位置，进入该目录执行 `codex plugin marketplace add .`，再安装插件。用 `codex plugin marketplace list` 确认当前注册的来源；如果同名市场指向 GitHub 或别的目录，先保留该来源的修改，再按上方“切换来源”命令移除市场注册并登记本地目录。长期修改保存到 `plugins/felix-workflows/`，入口 `SKILL.md` 和详细 `workflow.md` 可分别编辑，保存后重新安装，并在新聊天验证。

GitHub 来源使用上方 `marketplace upgrade` 命令；本地来源自行更新维护仓库，先保护并审阅自己的修改，再执行 `git pull --ff-only`，有分歧时保留双方内容并解决后重新安装。源码保存、本机安装与远端发布分别处理，旧聊天可能继续持有旧说明。

另一台电脑重新安装并自行连接 Notion、日历等服务；公开仓库本身无需访问邀请，业务账户权限仍由账户所有者授予。插件不会自动登录、连接账户或修改业务数据。

存在同名独立 Skill 或旧安装时，先比较全部文件，保留独有规则，确认插件可用并备份，再停用已被覆盖的副本。安装文件一致、真实会话行为和业务页面视觉显示分别验收。

0.5.0 的[迁移说明](six-domain-migration.md)和[自定义指南](customization.md)列出了完整文件对应与最新规则的保留方式。安装或更新不会替你处理原文已有的规则冲突。
