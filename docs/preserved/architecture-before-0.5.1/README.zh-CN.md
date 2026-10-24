<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme-banner-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/assets/readme-banner-light.svg">
    <img src="docs/assets/readme-banner-light.svg" alt="FELIX WORKFLOW — Felix's personal workflow library" width="100%">
  </picture>

  <p>用可编辑的 Markdown，构建自己的个人工作流库。</p>
  <p><strong>0.5.0 · 六类 Skill 入口 · 工作流 Markdown 独立编辑</strong></p>
  <p><a href="./README.md">English</a> · <strong>简体中文</strong></p>
  <p><a href="#快速开始">快速开始</a> · <a href="#六大领域">六大领域</a> · <a href="#自定义规则">自定义规则</a> · <a href="#文档导航">文档导航</a></p>
</div>

## 概览

FELIX WORKFLOW 将 Felix 的常用工作流程打包为一个 Codex 插件，覆盖知识、金融、日程、学习、研究和创作六大类。所有规则都保存在可以直接阅读和修改的文件中。

- **规则由你控制。** 分别编辑六类入口的 `SKILL.md`、完整工作流和配套 Markdown。
- **按任务选择流程。** 调用对应 Skill，再读取本次需要的参考文件。
- **保持执行方法一致。** 继承已确认要求，并核对实际完成的结果。

## 六大领域

**0.5.0 提供六个可调用的 Skill 入口。** 原有 13 项工作流的完整规则、参考文件、图标和示例均保留为独立模块；金融管理新增收支与投资复盘两份方法文件，不包含个人账户记录。

| 领域入口 | 调用名称 | 覆盖内容 | 独立文件 |
|:--|:--|:--|:--|
| 📚 [**知识管理**](plugins/felix-workflows/skills/knowledge-management/SKILL.md) | `$knowledge-management` | 笔记、数据库、知识结构与正文插图 | [3 个原有模块](docs/workflows.md#knowledge) |
| 💰 [**金融管理**](plugins/felix-workflows/skills/finance-management/SKILL.md) | `$finance-management` | 收支、对账与投资复盘 | [2 份新增方法](docs/workflows.md#finance) |
| 📅 [**日程管理**](plugins/felix-workflows/skills/schedule-management/SKILL.md) | `$schedule-management` | 依据权威来源维护学术日历与核对安排 | [1 个原有模块](docs/workflows.md#planning) |
| 🎓 [**学习管理**](plugins/felix-workflows/skills/learning-management/SKILL.md) | `$learning-management` | 概念理解、系统讲解与选课评估 | [3 个原有模块](docs/workflows.md#learning) |
| 🔎 [**研究管理**](plugins/felix-workflows/skills/research-management/SKILL.md) | `$research-management` | 行业结构与公司资料研究 | [2 个原有模块](docs/workflows.md#research) |
| 🎨 [**创作管理**](plugins/felix-workflows/skills/creative-management/SKILL.md) | `$creative-management` | 学科封面、行业封面与公司标识 | [4 个原有模块](docs/workflows.md#creative) |

## 快速开始

安装 Codex CLI 后，注册当前公开仓库的插件市场并安装：

```sh
codex plugin marketplace add Felix-Yang-369/Felix.Y-Workflow
codex plugin add felix-workflows@felix-workflows
```

开启新聊天，并点名使用对应工作流，例如：

```text
使用 $knowledge-management 审查这篇学科笔记，先提出具体优化方案。
```

GitHub 仓库名为 `Felix.Y-Workflow`，插件与市场的稳定标识仍为 `felix-workflows`。

本地源码安装、更新和跨设备使用见[安装指南](docs/installation.md#中文说明)。按任务另行连接所需服务；安装插件本身不会连接账户或修改数据。

## 工作方式

```text
plugins/felix-workflows/                 一个插件总包
├── plugin.json                         版本与插件身份
├── references/                         共用规则与完整迁移表
├── assets/                             FY 图标与原有资源
└── skills/<domain>/                    六类入口目录
    ├── SKILL.md                        可调用入口与模块选择
    ├── agents/openai.yaml              领域显示设置
    ├── assets/                         领域图标
    └── references/                     可独立编辑的完整模块
        └── <original-workflow>/
            ├── workflow.md             原工作流完整正文
            └── references/, assets/    原有参考与素材（如有）
```

入口按任务读取对应的完整工作流和配套规范，在授权范围内执行并验收。配套文档可分别编辑；[工作流目录](docs/workflows.md)链接了六个入口和全部保留模块。[迁移索引](plugins/felix-workflows/references/skill-map.md)保留旧名到文件的对应关系，旧模块名不作为额外的原生调用别名。

## 自定义规则

可编辑原件位于 `plugins/felix-workflows/`。

1. 修改入口选择逻辑时打开 `skills/<domain>/SKILL.md`；修改具体规则时打开其链接的 `references/<original-workflow>/workflow.md` 或配套 Markdown。
2. 修改并保存，保留稳定的 Skill 名称与相对路径。
3. 从本地市场重新安装，再开启新聊天使用。

```sh
codex plugin add felix-workflows@felix-workflows --json
```

源码结构、界面名称、跨设备维护与验收方式见[自定义指南](docs/customization.md#中文说明)。安装缓存由维护原件生成。

## 工作原则

- 提方案时只读；实际执行遵守本次授权范围。
- 保留有效内容、资源、目标身份和已确认要求。
- 保存内容的回读与实际界面显示分别验收。
- 个人数据和凭据保存在插件包之外。

这些工作流包含 Felix 的个人偏好。迁移使用时，先确认自己的工作区、目标和日历配置；学习进度由用户自行决定。

## 文档导航

| 文档 | 用途 |
|:--|:--|
| [English](README.md) | 英文默认首页 |
| [工作流目录](docs/workflows.md) | 六个入口、13 个保留模块与金融方法 |
| [安装指南](docs/installation.md#中文说明) | 安装、更新与跨设备使用 |
| [自定义指南](docs/customization.md#中文说明) | 编辑 Markdown、素材与显示设置 |
| [行为验收案例](docs/skill-acceptance.md) | 审阅工作流行为的场景 |
| [更新记录](CHANGELOG.md) | 完整保留的版本说明 |
| [迁移说明](docs/six-domain-migration.md) | 规则保留、旧名对应与验收边界 |
| [文档原文存档](docs/preserved/README.md) | 本次发布改写前的完整文档 |
| [旧版 README](docs/archive/readme-before-bilingual.md) | 完整保留的历史原文 |

维护者：[Felix Yang](https://github.com/Felix-Yang-369)。
