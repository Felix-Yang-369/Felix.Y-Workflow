# Installation · 安装指南

[English README](../README.md) · [中文首页](../README.zh-CN.md)

## Install from GitHub

The repository is public. Install the Codex CLI, then run:

```sh
codex plugin marketplace add Felix-Yang-369/Felix.Y-Workflow
codex plugin add felix-workflows@felix-workflows
```

Start a new conversation and confirm that the plugin is available. Invoke a Skill by its stable `$name`; installation does not cause every message to run every Skill.

## Install editable local source

Clone the repository into a location you control, then register that local directory:

```sh
git clone https://github.com/Felix-Yang-369/Felix.Y-Workflow.git
cd Felix.Y-Workflow
codex plugin marketplace add .
codex plugin add felix-workflows@felix-workflows
```

Use `codex plugin marketplace list` to check which source directory is registered. Edit the source under `plugins/felix-workflows/`; reinstall after saving and verify in a new conversation. Old conversations may retain earlier instructions.

## Update and use another computer

For a GitHub-backed marketplace:

```sh
codex plugin marketplace upgrade felix-workflows
codex plugin add felix-workflows@felix-workflows
```

For an editable local checkout, preserve and review local changes before pulling source updates. Refresh the plugin after updating the checkout. Source changes and GitHub publication are separate from local installation.

On another computer, repeat installation and connect the services needed by your tasks. No invitation is required to read this public repository. Access to Notion, calendars, or other accounts is granted separately by their owner.

If similarly named standalone Skills or an older plugin are present, compare their complete files first. Preserve unique rules, confirm the plugin works, and back up any standalone copy before disabling it. Avoid duplicate entries.

## Verify the result

```sh
codex plugin list --marketplace felix-workflows --json
```

Check the installed and enabled state, then test a harmless workflow in a new conversation. File consistency, actual Skill behavior, and visual checks of changed business pages are separate forms of verification.

## 中文说明

本仓库现为公开仓库，安装命令见上方；仓库名为 `Felix.Y-Workflow`，插件与市场标识继续使用 `felix-workflows`。

需要自行编辑时，克隆到自己控制的位置，进入该目录执行 `codex plugin marketplace add .`，再安装插件。用 `codex plugin marketplace list` 确认当前注册的来源；长期修改保存到 `plugins/felix-workflows/`，保存后重新安装，并在新聊天验证。

GitHub 来源使用上方更新命令。本地维护仓库先保护并审阅自己的修改，再拉取更新。源码保存、本机安装与远端发布分别处理，旧聊天可能继续持有旧说明。

另一台电脑重新安装并自行连接 Notion、日历等服务；公开仓库本身无需访问邀请，业务账户权限仍由账户所有者授予。插件不会自动登录、连接账户或修改业务数据。

存在同名独立 Skill 或旧安装时，先比较全部文件，保留独有规则，确认插件可用并备份，再停用已被覆盖的副本。安装文件一致、真实会话行为和业务页面视觉显示分别验收。
