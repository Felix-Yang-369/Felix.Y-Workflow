# Workflow catalog · 工作流目录

[English README](../README.md) · [中文首页](../README.zh-CN.md)

The six domains are a navigation map. Each link below opens a current Skill entry. Financial workflows are proposed and are not packaged yet.

六大领域用于导航；下方链接均对应现有 Skill。金融工作流尚未打包实现。

<a id="knowledge"></a>
## Knowledge · 知识管理

| Workflow | Entry | Responsibility |
|:--|:--|:--|
| Academic databases · 学科知识库管理 | [`$notion-academic-database-manager`](../plugins/felix-workflows/skills/notion-academic-database-manager/SKILL.md) | Views, fields, and page layouts · 视图、字段与页面布局 |
| Academic notes · 学科笔记 | [`$notion-note-steward`](../plugins/felix-workflows/skills/notion-note-steward/SKILL.md) | Content, structure, formulas, and verification · 正文、结构、公式与验收 |
| Academic illustrations · 学科插图 | [`$academic-illustration`](../plugins/felix-workflows/skills/academic-illustration/SKILL.md) | Relevant images beside the knowledge they explain · 就近配合知识点的正文插图 |

<a id="finance"></a>
## Finance · 金融管理

Planned: cash-flow classification and reconciliation; transaction archives and portfolio reviews. Scope and implementation will be confirmed in a later release.

规划方向：收支分类与对账、交易档案与投资复盘；具体范围与实现以后续发布为准。

<a id="planning"></a>
## Planning · 日程管理

| Workflow | Entry | Responsibility |
|:--|:--|:--|
| Academic calendars · 日程管理 | [`$schedule-management`](../plugins/felix-workflows/skills/schedule-management/SKILL.md) | iCloud academic calendars through device-appropriate clients · 通过合适客户端维护 iCloud 学术日历 |

<a id="learning"></a>
## Learning · 学习管理

| Workflow | Entry | Responsibility |
|:--|:--|:--|
| Abstract concepts · 抽象知识讲解 | [`$abstract-knowledge-explainer`](../plugins/felix-workflows/skills/abstract-knowledge-explainer/SKILL.md) | Concrete examples, abstraction, definitions, and reasoning · 具体例子、抽象、定义与推理 |
| Concrete systems · 具象知识讲解 | [`$concrete-knowledge-explainer`](../plugins/felix-workflows/skills/concrete-knowledge-explainer/SKILL.md) | Structure, components, dynamic processes, and calculation · 结构、部件、动态过程与计算 |
| Course evaluation · 课程评估 | [`$course-evaluation`](../plugins/felix-workflows/skills/course-evaluation/SKILL.md) | Catalog, syllabus, software, and instructor evidence · 课程目录、大纲、软件及教师评价 |

<a id="research"></a>
## Research · 研究管理

| Workflow | Entry | Responsibility |
|:--|:--|:--|
| Industry research · 行业笔记 | [`$notion-industry-steward`](../plugins/felix-workflows/skills/notion-industry-steward/SKILL.md) | Classification, hierarchy, and industry analysis · 行业分类、层级与分析 |
| Company research · 公司笔记 | [`$notion-company-steward`](../plugins/felix-workflows/skills/notion-company-steward/SKILL.md) | Concise company profiles and existing fields · 简短公司概览与现有企业属性 |

<a id="creative"></a>
## Creative · 创作管理

| Workflow | Entry | Responsibility |
|:--|:--|:--|
| Discipline covers · 学科封面 | [`$secondary-discipline-cover`](../plugins/felix-workflows/skills/secondary-discipline-cover/SKILL.md) | Diagram-based discipline covers and series · 图解学科封面与系列设计 |
| Photorealistic covers · 写实学科封面 | [`$photorealistic-discipline-cover`](../plugins/felix-workflows/skills/photorealistic-discipline-cover/SKILL.md) | Realistic scenes and materials with a discipline title · 写实场景、材质与学科标题 |
| Industry covers · 行业封面 | [`$notion-cover-designer`](../plugins/felix-workflows/skills/notion-cover-designer/SKILL.md) | Consistent covers for industries and subindustries · 行业与细分行业系列封面 |
| Company logos · 公司 Logo | [`$company-logo`](../plugins/felix-workflows/skills/company-logo/SKILL.md) | Verified official marks, icons, and requested original designs · 核实的官方标识、图标及明确要求的原创设计 |

## Example requests · 调用示例

```text
Use $notion-note-steward to review this academic note and propose improvements.
使用 $abstract-knowledge-explainer 讲清这个概念，先从一个可计算的例子开始。
Use $course-evaluation to compare these courses using current official sources.
使用 $schedule-management 核对本学期日历，先检查来源与已有事件。
```

The two explainers share the current teaching thread: answer a local question at the point of difficulty and return to the unfinished example or exercise. The calendar workflow uses iCloud as the shared data layer, Apple Calendar on macOS and Notion Calendar on Windows; a Notion database calendar does not replace those calendars.

两项讲解技能保留当前主线，局部追问直接解决卡点，再回到未完成的例子或练习。日程管理以 iCloud 为共享数据层，macOS 使用 Apple Calendar，Windows 使用 Notion Calendar；Notion 数据库日历不替代这些日历。
