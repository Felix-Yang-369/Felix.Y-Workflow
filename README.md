<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme-banner-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/assets/readme-banner-light.svg">
    <img src="docs/assets/readme-banner-light.svg" alt="FELIX WORKFLOW — Felix's personal workflow library" width="100%">
  </picture>

  <p>Your personal workflow library, built from editable Markdown.</p>
  <p><strong>0.5.1 · Academic Notes and Industry Notes first</strong></p>
  <p><strong>English</strong> · <a href="README.zh-CN.md">简体中文</a></p>
  <p><a href="#quick-start">Quick Start</a> · <a href="#six-domains">Six Domains</a> · <a href="#customize-your-workflow">Customize</a> · <a href="#documentation">Documentation</a></p>
</div>

## Overview

FELIX WORKFLOW packages Felix's repeatable workflows into one Codex plugin. It brings together academic notes, industry notes, finance, calendars, learning, and personal creative works, with the instructions kept in files you can read and edit.

- **Make the rules yours.** Edit a domain’s `SKILL.md` and each full workflow or method file independently.
- **Use focused workflows.** Choose the Skill for your task, then load the relevant references.
- **Keep a consistent method.** Carry confirmed requirements through execution and check the actual result.

## Six Domains

**Version 0.5.1 exposes six entries, with Academic Notes and Industry Notes first.** All 13 original workflow modules and resources are retained, with user-approved rule refinements. Note covers and company logos belong to the corresponding note entry; Creative manages personal blog, Douyin, and Xiaohongshu works.

| Order | Domain entry | Invoke | Responsibility | Editable modules |
|:--|:--|:--|:--|:--|
| 1 | [Academic Notes](plugins/felix-workflows/skills/academic-notes/SKILL.md) | `$academic-notes` | Academic databases, notes, illustrations, and both discipline-cover styles | [5 preserved modules](docs/workflows.md#academic-notes) |
| 2 | [Industry Notes](plugins/felix-workflows/skills/industry-notes/SKILL.md) | `$industry-notes` | Industry and company notes, fields, industry covers, and company logos | [4 preserved modules](docs/workflows.md#industry-notes) |
| 3 | [Finance](plugins/felix-workflows/skills/finance-management/SKILL.md) | `$finance-management` | Cash flow, reconciliation, and investment reviews | [2 finance method files](docs/workflows.md#finance) |
| 4 | [Planning](plugins/felix-workflows/skills/schedule-management/SKILL.md) | `$schedule-management` | Academic calendars and schedule checks | [1 preserved module](docs/workflows.md#planning) |
| 5 | [Learning](plugins/felix-workflows/skills/learning-management/SKILL.md) | `$learning-management` | Concepts, systems, and course-fit decisions | [3 preserved modules](docs/workflows.md#learning) |
| 6 | [Creative](plugins/felix-workflows/skills/creative-management/SKILL.md) | `$creative-management` | Personal blog, Douyin, and Xiaohongshu works | [3 platform modules](docs/workflows.md#creative) |

> Version 0.5.1 is available from GitHub and editable local source. For source you can maintain yourself, follow the [local installation guide](docs/installation.md).

Academic-note rules now include the fixed Introduction template and cover columns, optional fifth-level Core Questions, preserved user layouts, H1 `and` → `&`, and the confirmed database fields, progress, difficulty, and theme-color rules. See the [changelog](CHANGELOG.md) for the full update.

## Quick Start

With the Codex CLI installed, register this public repository's marketplace and install the plugin:

```sh
codex plugin marketplace add Felix-Yang-369/Felix.Y-Workflow
codex plugin add felix-workflows@felix-workflows
```

Start a new conversation and invoke a workflow, for example:

```text
Use $academic-notes to review this academic note and propose improvements.
```

The repository name is `Felix.Y-Workflow`; the stable plugin and marketplace identifiers remain `felix-workflows`.

See the [installation guide](docs/installation.md) for local-source installs, updates, and setup on another computer. Connect the services needed by your task separately; installation alone does not connect accounts or modify data.

## How It Works

```text
plugins/felix-workflows/                 one plugin
├── plugin.json                         version and plugin identity
├── references/                         shared rules and full migration map
├── assets/                             FY icon and preserved resources
└── skills/<domain>/                    six domain directories
    ├── SKILL.md                        callable entry and module routing
    ├── agents/openai.yaml              domain display settings
    ├── assets/                         domain icon
    └── references/                     independently editable modules
        └── <original-workflow>/
            ├── workflow.md             complete original instructions
            └── references/, assets/    original supporting files, when present
```

A domain Skill selects the relevant complete workflow and its supporting rules, then checks the result within the authorized scope. Supporting documents can be edited individually. The [workflow catalog](docs/workflows.md) links all six entries and every preserved module. The [migration map](plugins/felix-workflows/references/skill-map.md) maps old names to files; old module names are not additional callable Skill aliases.

## Customize Your Workflow

The editable source lives in `plugins/felix-workflows/`.

1. Open `skills/<domain>/SKILL.md` to edit routing, or its linked `references/<original-workflow>/workflow.md` and supporting Markdown to edit detailed rules.
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
| [Migration notes](docs/six-domain-migration.md) | Preserved rules, old-name mapping, and verification limits |
| [Preserved documentation](docs/preserved/README.md) | Exact source before this publication edit |
| [Previous README](docs/archive/readme-before-bilingual.md) | Historical source preserved in full |

See the [current architecture](docs/architecture.md) for responsibilities and module ownership.

Maintained by [Felix Yang](https://github.com/Felix-Yang-369).
