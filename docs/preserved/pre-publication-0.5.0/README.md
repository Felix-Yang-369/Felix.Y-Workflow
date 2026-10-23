<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme-banner-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/assets/readme-banner-light.svg">
    <img src="docs/assets/readme-banner-light.svg" alt="FELIX WORKFLOW — Felix's personal workflow library" width="100%">
  </picture>

  <p>Your personal workflow library, built from editable Markdown.</p>
  <p><strong>English</strong> · <a href="./README.zh-CN.md">简体中文</a></p>
  <p><a href="#quick-start">Quick Start</a> · <a href="#six-domains">Six Domains</a> · <a href="#customize-your-workflow">Customize</a> · <a href="#documentation">Documentation</a></p>
</div>

<!-- six-domain-migration:start -->
> **0.5.0 local migration / 本地六入口迁移：** The plugin now exposes six domain Skills; the 13 original workflows remain complete editable reference modules. 金融入口新增收支与投资方法。下文原有说明和示例完整保留，其中十三个旧名称、Finance planned 和旧结构属于迁移前记录，不再作为当前入口说明。

| Current entry 当前入口 | Invoke 调用 |
|---|---|
| [知识管理](plugins/felix-workflows/skills/knowledge-management/SKILL.md) | `$knowledge-management` |
| [金融管理](plugins/felix-workflows/skills/finance-management/SKILL.md) | `$finance-management` |
| [日程管理](plugins/felix-workflows/skills/schedule-management/SKILL.md) | `$schedule-management` |
| [学习管理](plugins/felix-workflows/skills/learning-management/SKILL.md) | `$learning-management` |
| [研究管理](plugins/felix-workflows/skills/research-management/SKILL.md) | `$research-management` |
| [创作管理](plugins/felix-workflows/skills/creative-management/SKILL.md) | `$creative-management` |

Full migration map / 完整对应：[模块索引](plugins/felix-workflows/references/skill-map.md)。原文中旧名字用于查找参考模块，不是宿主原生别名。当前入口与详细 Markdown 均可单独编辑。
<!-- six-domain-migration:end -->


## Overview

FELIX WORKFLOW packages Felix's repeatable workflows into one Codex plugin. It brings together knowledge organization, learning, research, calendar management, and visual creation, with the instructions kept in files you can read and edit.

- **Make the rules yours.** Edit a workflow's `SKILL.md` and its supporting Markdown files.
- **Use focused workflows.** Choose the Skill for your task, then load the relevant references.
- **Keep a consistent method.** Carry confirmed requirements through execution and check the actual result.

## Six Domains

Six domains provide a navigation map for the library. The current package contains **13 Skills** across five domains; Finance is planned.

| Domain | What it covers | Current workflows |
|:--|:--|:--|
| 📚 **Knowledge** | Notes, databases, structure, and supporting illustrations | [3 Skills](docs/workflows.md#knowledge) |
| 💰 **Finance** | Cash flow, reconciliation, and investment reviews | [Planned](docs/workflows.md#finance) |
| 📅 **Planning** | Source-backed academic calendars and schedule checks | [1 Skill](docs/workflows.md#planning) |
| 🎓 **Learning** | Concepts, systems, and course-fit decisions | [3 Skills](docs/workflows.md#learning) |
| 🔎 **Research** | Industry structure and company information | [2 Skills](docs/workflows.md#research) |
| 🎨 **Creative** | Discipline covers, industry covers, and company logos | [4 Skills](docs/workflows.md#creative) |

## Quick Start

With the Codex CLI installed, register this public repository's marketplace and install the plugin:

```sh
codex plugin marketplace add Felix-Yang-369/Felix.Y-Workflow
codex plugin add felix-workflows@felix-workflows
```

Start a new conversation and invoke a workflow, for example:

```text
Use $notion-note-steward to review this academic note and propose improvements.
```

The repository name is `Felix.Y-Workflow`; the stable plugin and marketplace identifiers remain `felix-workflows`.

See the [installation guide](docs/installation.md) for local-source installs, updates, and setup on another computer. Connect the services needed by your task separately; installation alone does not connect accounts or modify data.

## How It Works

```text
FELIX WORKFLOW · one plugin
├── Skills               task entry points and procedures
├── references/          detailed rules and examples within each Skill
├── assets/              icons and supporting visual resources
└── agents/openai.yaml   each Skill's display settings
```

A Skill describes when to use a workflow, what to read, which steps to follow, and how to verify its result. Supporting documents can be edited individually. The [workflow catalog](docs/workflows.md) links every current entry.

## Customize Your Workflow

The editable source lives in `plugins/felix-workflows/`.

1. Open `skills/<skill-name>/SKILL.md` or one of its linked reference files.
2. Save your changes while preserving stable Skill names and relative paths.
3. Reinstall from your local marketplace, then use a new conversation.

```sh
codex plugin add felix-workflows@felix-workflows --json
```

Follow the [customization guide](docs/customization.md) for source layout, UI metadata, cross-device maintenance, and verification. The installed cache is generated from the editable source.

## Working Principles

- A proposal is read-only; execution follows the scope you authorize.
- Preserve useful content, resources, identity, and confirmed requirements.
- Check saved content and actual visual display separately.
- Keep personal records and credentials outside the plugin package.

These workflows include Felix's preferences. When adapting them, confirm your own workspace, targets, and calendar setup. Learning progress remains a user decision.

## Documentation

| Document | Purpose |
|:--|:--|
| [简体中文](README.zh-CN.md) | Complete Chinese README |
| [Workflow catalog](docs/workflows.md) | Current Skills, domain map, and example requests |
| [Installation](docs/installation.md) | Install, update, and use another computer |
| [Customization](docs/customization.md) | Edit Markdown, assets, and display settings |
| [Behavior acceptance cases](docs/skill-acceptance.md) | Review scenarios for workflow behavior |
| [Changelog](CHANGELOG.md) | Preserved version notes |
| [Previous README](docs/archive/readme-before-bilingual.md) | Historical source preserved in full |

Maintained by [Felix Yang](https://github.com/Felix-Yang-369).
