# Workflow catalog · 工作流目录

[English README](../README.md) · [中文首页](../README.zh-CN.md)

Version **0.5.0** has six callable domain entries. Each loads the relevant complete module below. All 13 original workflows and supporting resources are retained; Finance adds two method files.

版本 **0.5.0** 提供六个入口，按任务读取下方完整模块。原 13 项工作流与配套资源全部保留，金融管理新增两份方法。下表中的旧名标识用于查找可编辑文件，不是独立调用别名。

<a id="knowledge"></a>
## Knowledge · 知识管理

Entry / 入口：[`$knowledge-management`](../plugins/felix-workflows/skills/knowledge-management/SKILL.md)。

| Workflow | Editable module · 原名 | Responsibility |
|:--|:--|:--|
| Academic databases · 学科知识库管理 | [`notion-academic-database-manager`](../plugins/felix-workflows/skills/knowledge-management/references/notion-academic-database-manager/workflow.md) | Views, fields, and page layouts · 视图、字段与页面布局 |
| Academic notes · 学科笔记 | [`notion-note-steward`](../plugins/felix-workflows/skills/knowledge-management/references/notion-note-steward/workflow.md) | Content, structure, formulas, and verification · 正文、结构、公式与验收 |
| Academic illustrations · 学科插图 | [`academic-illustration`](../plugins/felix-workflows/skills/knowledge-management/references/academic-illustration/workflow.md) | Relevant images beside the knowledge they explain · 就近配合知识点的正文插图 |

<a id="finance"></a>
## Finance · 金融管理

Entry / 入口：[`$finance-management`](../plugins/felix-workflows/skills/finance-management/SKILL.md)。

| Method | Editable file | Responsibility |
|:--|:--|:--|
| Cash flow · 收支与对账 | [cashflow.md](../plugins/felix-workflows/skills/finance-management/references/cashflow.md) | Period, currency, classification, reconciliation, and missing records · 期间、币种、分类、核对与缺失记录 |
| Portfolio · 投资复盘 | [portfolio.md](../plugins/felix-workflows/skills/finance-management/references/portfolio.md) | Transaction archives, positions, fees, and return review · 交易档案、持仓、费用与收益复盘 |

These are new instruction files, not imported personal records or an account connection.

这两份文件是新增方法规范，不含个人财务记录，也不代表已连接账户。

<a id="planning"></a>
## Planning · 日程管理

Entry / 入口：[`$schedule-management`](../plugins/felix-workflows/skills/schedule-management/SKILL.md)。

| Workflow | Editable module · 原名 | Responsibility |
|:--|:--|:--|
| Academic calendars · 日程管理 | [`schedule-management`](../plugins/felix-workflows/skills/schedule-management/references/schedule-management/workflow.md) | iCloud academic calendars through device-appropriate clients · 通过合适客户端维护 iCloud 学术日历 |

<a id="learning"></a>
## Learning · 学习管理

Entry / 入口：[`$learning-management`](../plugins/felix-workflows/skills/learning-management/SKILL.md)。

| Workflow | Editable module · 原名 | Responsibility |
|:--|:--|:--|
| Abstract concepts · 抽象知识讲解 | [`abstract-knowledge-explainer`](../plugins/felix-workflows/skills/learning-management/references/abstract-knowledge-explainer/workflow.md) | Concrete examples, abstraction, definitions, and reasoning · 具体例子、抽象、定义与推理 |
| Concrete systems · 具象知识讲解 | [`concrete-knowledge-explainer`](../plugins/felix-workflows/skills/learning-management/references/concrete-knowledge-explainer/workflow.md) | Structure, components, dynamic processes, and calculation · 结构、部件、动态过程与计算 |
| Course evaluation · 课程评估 | [`course-evaluation`](../plugins/felix-workflows/skills/learning-management/references/course-evaluation/workflow.md) | Catalog, syllabus, software, and instructor evidence · 课程目录、大纲、软件及教师评价 |

<a id="research"></a>
## Research · 研究管理

Entry / 入口：[`$research-management`](../plugins/felix-workflows/skills/research-management/SKILL.md)。

| Workflow | Editable module · 原名 | Responsibility |
|:--|:--|:--|
| Industry research · 行业笔记 | [`notion-industry-steward`](../plugins/felix-workflows/skills/research-management/references/notion-industry-steward/workflow.md) | Classification, hierarchy, and industry analysis · 行业分类、层级与分析 |
| Company research · 公司笔记 | [`notion-company-steward`](../plugins/felix-workflows/skills/research-management/references/notion-company-steward/workflow.md) | Concise company profiles and existing fields · 简短公司概览与现有企业属性 |

<a id="creative"></a>
## Creative · 创作管理

Entry / 入口：[`$creative-management`](../plugins/felix-workflows/skills/creative-management/SKILL.md)。

| Workflow | Editable module · 原名 | Responsibility |
|:--|:--|:--|
| Discipline covers · 学科封面 | [`secondary-discipline-cover`](../plugins/felix-workflows/skills/creative-management/references/secondary-discipline-cover/workflow.md) | Diagram-based discipline covers and series · 图解学科封面与系列设计 |
| Photorealistic covers · 写实学科封面 | [`photorealistic-discipline-cover`](../plugins/felix-workflows/skills/creative-management/references/photorealistic-discipline-cover/workflow.md) | Realistic scenes and materials with a discipline title · 写实场景、材质与学科标题 |
| Industry covers · 行业封面 | [`notion-cover-designer`](../plugins/felix-workflows/skills/creative-management/references/notion-cover-designer/workflow.md) | Consistent covers for industries and subindustries · 行业与细分行业系列封面 |
| Company logos · 公司 Logo | [`company-logo`](../plugins/felix-workflows/skills/creative-management/references/company-logo/workflow.md) | Verified official marks, icons, and requested original designs · 核实的官方标识、图标及明确要求的原创设计 |

## Example requests · 调用示例

```text
Use $knowledge-management to review this academic note and propose improvements.
使用 $finance-management 核对我提供的本月流水，区分已核对与待确认项目。
使用 $schedule-management 核对本学期日历，先检查来源与已有事件。
使用 $learning-management 讲清这个概念，先从一个可计算的例子开始。
Use $learning-management to compare these courses using current official sources.
Use $research-management to review the industry and company information.
使用 $creative-management 为指定学科制作封面，沿用已确认系列。
```

The two explainers share the current teaching thread: answer a local question at the point of difficulty and return to the unfinished example or exercise. The calendar workflow uses iCloud as the shared data layer, Apple Calendar on macOS and Notion Calendar on Windows; a Notion database calendar does not replace those calendars.

两项讲解技能保留当前主线，局部追问直接解决卡点，再回到未完成的例子或练习。日程管理以 iCloud 为共享数据层，macOS 使用 Apple Calendar，Windows 使用 Notion Calendar；Notion 数据库日历不替代这些日历。
