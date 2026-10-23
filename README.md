<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme-banner-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/assets/readme-banner-light.svg">
    <img src="docs/assets/readme-banner-light.svg" alt="FELIX WORKFLOW — Felix's personal workflow library" width="100%">
  </picture>

  <p>Your personal workflow library, built from editable Markdown.</p>
  <p><strong>0.5.0 · Six Skill entries · Fully editable workflow modules</strong></p>
  <p><strong>English</strong> · <a href="./README.zh-CN.md">简体中文</a></p>
  <p><a href="#quick-start">Quick Start</a> · <a href="#six-domains">Six Domains</a> · <a href="#customize-your-workflow">Customize</a> · <a href="#documentation">Documentation</a></p>
</div>

## Overview

FELIX WORKFLOW packages Felix's repeatable workflows into one Codex plugin. It brings together knowledge organization, finance, calendar management, learning, research, and visual creation, with the instructions kept in files you can read and edit.

- **Make the rules yours.** Edit a domain’s `SKILL.md` and each full workflow or method file independently.
- **Use focused workflows.** Choose the Skill for your task, then load the relevant references.
- **Keep a consistent method.** Carry confirmed requirements through execution and check the actual result.

## Six Domains

**0.5.0 exposes six callable Skill entries.** All 13 original workflows, their rules, supporting files, icons, and examples remain complete reference modules. Finance adds two method files for cash flow and portfolio reviews; it does not include personal financial records.

| Domain entry | Invoke | What it covers | Editable modules |
|:--|:--|:--|:--|
| 📚 [**Knowledge**](plugins/felix-workflows/skills/knowledge-management/SKILL.md) | `$knowledge-management` | Notes, databases, structure, and supporting illustrations | [3 preserved modules](docs/workflows.md#knowledge) |
| 💰 [**Finance**](plugins/felix-workflows/skills/finance-management/SKILL.md) | `$finance-management` | Cash flow, reconciliation, and investment reviews | [2 new method files](docs/workflows.md#finance) |
| 📅 [**Planning**](plugins/felix-workflows/skills/schedule-management/SKILL.md) | `$schedule-management` | Source-backed academic calendars and schedule checks | [1 preserved module](docs/workflows.md#planning) |
| 🎓 [**Learning**](plugins/felix-workflows/skills/learning-management/SKILL.md) | `$learning-management` | Concepts, systems, and course-fit decisions | [3 preserved modules](docs/workflows.md#learning) |
| 🔎 [**Research**](plugins/felix-workflows/skills/research-management/SKILL.md) | `$research-management` | Industry structure and company information | [2 preserved modules](docs/workflows.md#research) |
| 🎨 [**Creative**](plugins/felix-workflows/skills/creative-management/SKILL.md) | `$creative-management` | Discipline covers, industry covers, and company logos | [4 preserved modules](docs/workflows.md#creative) |

## Quick Start

With the Codex CLI installed, register this public repository's marketplace and install the plugin:

```sh
codex plugin marketplace add Felix-Yang-369/Felix.Y-Workflow
codex plugin add felix-workflows@felix-workflows
```

Start a new conversation and invoke a workflow, for example:

```text
Use $knowledge-management to review this academic note and propose improvements.
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

Maintained by [Felix Yang](https://github.com/Felix-Yang-369).
