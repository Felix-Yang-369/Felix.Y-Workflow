# Customization · 自定义指南

[English README](../README.md) · [中文首页](../README.zh-CN.md)

## Source layout

`plugins/felix-workflows/` is the editable plugin source. Each installed cache is generated from it.

```text
.agents/plugins/marketplace.json      marketplace catalog
plugins/felix-workflows/
  plugin.json                        portable plugin manifest
  .codex-plugin/plugin.json          compatibility manifest
  assets/icon.svg                    plugin icon
  skills/<skill-name>/
    SKILL.md                         workflow entry and instructions
    references/                      detailed Markdown and examples
    assets/                          supporting resources
    agents/openai.yaml               display metadata
```

## Edit a workflow

1. Read its `SKILL.md` and any reference file relevant to your change.
2. Edit the maintained source, preserving useful rules, relative links, assets, and existing user changes.
3. Keep directory names, YAML `name`, and `$name` invocation identifiers stable. A new Skill needs matching names and a description that states when it should be used.
4. Validate the changed files and referenced resources.
5. Reinstall from the local marketplace and check the installed files. Use a new conversation to verify actual behavior.

Detailed guidance lives in the workflow's linked reference files. For example, the [academic database rules](../plugins/felix-workflows/skills/notion-academic-database-manager/SKILL.md) and [academic note format guide](../plugins/felix-workflows/skills/notion-note-steward/references/format-guide.md) remain separately editable.

## Display names and visual assets

Per-Skill display names, short descriptions, default prompts, icons, and accent colors live in `agents/openai.yaml`. Stable English identifiers can coexist with Chinese or bilingual interface names. The five Notion workflows use Chinese display names without a “Notion” prefix.

The two plugin manifests reference `assets/icon.svg`. The README banners use Felix's FY mark. Keep their identity, version, and presentation consistent. Check icons at small sizes on light and dark backgrounds. Individual Skills retain distinguishable icons and colors; a missing optional icon does not disable a Skill.

The original seven-icon preview is preserved here:

![Original seven Skill icons](../plugins/felix-workflows/assets/skill-icons-preview.png)

The two explainer icons use converging nodes and connected components to distinguish abstract and concrete teaching.

## Preserve workflow boundaries

- Academic-note work distinguishes proposals, content improvements, formatting, and structural changes.
- Learning progress is user-maintained; note improvements do not authorize a progress change.
- Discipline-cover work follows the requested deliverable: a prompt, an image, or application to a named page. Industry covers retain existing artwork unless replacement is requested.
- Company-logo work defaults to official brand marks; it does not imply redesigning a company's identity.
- Existing accepted versions, page resources, accurate targets, and relevant requirements remain in force across local corrections.

## Cross-device maintenance and validation

Keep credentials, account data, local application databases, generated caches, and device-specific configuration outside the package. Avoid references that depend on one machine's absolute paths.

Review source changes before any Git commit or publication. Another computer receives published changes after updating its source and refreshing installation; saving source locally does not hot-update every conversation or change Notion pages.

Use the [behavior acceptance cases](skill-acceptance.md). Check manifests, Skill frontmatter, relative links, referenced assets, and source/cache consistency. These static checks do not prove real conversation behavior or business-page rendering. Report saved content, actual visual display, and remaining gaps separately.

## 中文说明

`plugins/felix-workflows/` 是唯一维护原件。每个 Skill 的规则位于自己的 `SKILL.md`，详细说明与模板放在同目录的 `references/`、`assets/`；不要把安装缓存作为长期编辑位置。

编辑前读取相关入口和参考文件，保留现有内容、用户修改、相对链接与资源。目录名、YAML `name` 和 `$name` 是稳定英文标识；新增 Skill 时保持名称匹配，并明确触发条件。界面中文名称、简介、默认提示词、图标与主题色在 `agents/openai.yaml` 中维护。五项 Notion 工作流的显示名不以“Notion”开头。

两个插件清单引用同一插件图标 `assets/icon.svg`；README 横幅采用 FY 标识。身份、版本与显示设置需要保持一致。各 Skill 的独立颜色与图形继续保留，图标调整后检查小尺寸与浅深背景。上方保留原有七项图标预览；抽象、具象讲解图标分别表达汇聚节点与连接部件。

学科笔记区分方案、内容、排版和结构任务；学习进度由用户维护。学科封面按本次要求交付提示词、图片或应用结果；行业封面无更换要求时保留已有版本。公司 Logo 默认使用官方标识，不代表重新设计品牌。局部修正继续保留已确认要求和采用版本。

保存后校验并重新安装，再在新聊天验证。跨设备发布前审阅改动，另一设备更新源码并刷新安装；源码保存不代表全部聊天热更新，也不会自动修改 Notion。

凭据、真实账户资料、Notion 本地数据库、生成缓存及设备配置保存在包外。静态文件检查、真实会话行为、业务页面内容回读和视觉验收分别报告。详细行为标准继续以[验收案例](skill-acceptance.md)及各 Skill 规范为准。
