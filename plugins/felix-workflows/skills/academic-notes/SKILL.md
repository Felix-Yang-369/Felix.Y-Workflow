---
name: academic-notes
description: 为 Felix 维护 Notion 中的学科知识树、学科数据库、学科正文、正文插图或学科封面时使用；面向个人博客和社交平台的作品使用创作管理
---

# 学科笔记

维护 Felix 在 Notion 中的学科知识库，涵盖数据库组织、笔记内容、正文插图及学科封面；根据当前任务读取对应模块。先读[公共执行规则](../../references/execution-rules.md)，再按任务读取对应完整模块，不以入口概述替代其详细规则。

| 当前任务 | 必须读取的完整模块 |
|---|---|
| 学科数据库视图、属性、布局或规范本身 | [学科数据库规范](references/notion-academic-database-manager/workflow.md) |
| 学科正文、章节、知识归属、公式、列表或双栏 | [学科笔记规范](references/notion-note-steward/workflow.md)，配套参考按下方任务条件读取 |
| 配合具体知识点的正文插图或概念图 | [学科插图](references/academic-illustration/workflow.md)，并按目标正文需要读取相关格式规则 |
| 学科图解封面、系列海报或封面提示词 | [学科封面](references/secondary-discipline-cover/workflow.md)及其要求的模板与系列资源 |
| 写实摄影、真实场景或材质的学科封面 | [写实学科封面](references/photorealistic-discipline-cover/workflow.md)及其模板与参考图 |

正文类任务均读取[共同执行与验收规则](references/notion-note-steward/references/completion-workflow.md)；新建、补充或深化知识时读取[教材与讲义参考规则](references/notion-note-steward/references/academic-sources.md)，整理格式时读取[格式指南](references/notion-note-steward/references/format-guide.md)。混合任务读取实际涉及的规范，纯格式整理不自动扩展为内容研究。

## 学科正文架构与知识条目

- **列表与表格（轻度偏好）**：表达同样清楚时，优先原生有序列表，适当减少表格；多维横向对照、数据矩阵等内容用表格明显更直观时仍使用表格。这不是禁用表格的硬性规则，以内容清晰和实际可读性为先；详见[列表与表格的选择](references/notion-note-steward/workflow.md#列表与表格的选择轻度偏好)

- 学科导论开头固定为 `INTRODUCTION 导论 → A. Overview 概述 → a. Definition 定义 → i. Definition 定义 / ii. Position 定位`，后两项使用原生罗马数字列表。首个 Definition 的正文写 `简称, 全称, 解释`，无通行简称时写 `全称, 解释`；分隔固定为半角逗号加一个空格。具体结构与学科父页的数据库位置见[固定导论模板](references/notion-note-steward/workflow.md#学科导论固定模板)
- Core Questions 按需作为 Position 后的第五级原生罗马数字列表项，不默认独立设二级章节；起源或历史仅在一级学科确有需要时考虑，末端专题笔记不默认设置，已有有效内容保留
- Connections 学科联系作为低频右侧补充：优先在导论封面下方按需出现一处，其他章节仅有独特理解价值时少量添加，不按章重复。插图不标注来源；只有单看图意不清时才补一行简短解释，图内已有讲解时不再加外部说明
- 新建正文双栏默认从左侧 H3 三级标题开始：H3 位于左栏顶部，其下 H4 和所属正文留在同一左栏；右侧相关插图、例题等从这组双栏顶部与 H3 并列起头。已有用户布局继续保留，导论 Overview 与封面从 H2 并列的规则继续适用
- 导论固定采用 Overview 在左、该学科当前封面在右的双栏，H1 保持在双栏外；新建双栏默认 6:4，可视内容采用 5:5 或 7:3。保留已有比例及用户手动调整，非 5:5 也不自动改动；具体见[双栏规则](references/notion-note-steward/workflow.md#学科笔记的正文与说明区)
- 新建或获准重整学科正文时，一级实质章节优先 4–7 章，以 5–6 章为佳；不含未编号的 INTRODUCTION，不把该数量机械套到每组二三级标题
- 一级章节（H1）的英文部分，独立单词 `and`（含 `AND`、`And` 等大小写）统一替换为 `&`，两侧各留一个空格；其余英文保持全大写。该替换仅限一级章节名
- 章节英文名称优先 1–4 个单词，以 2–3 个为佳；二三级标题优先描述学科对象、本质结构与内在分类，参考 `Group Basics 群基础`、`Group Types 群类型`、`Group Structures 群结构`、`Group Morphisms 群态射`、`Group Actions 群作用` 等命名风格，不照搬固定章节清单
- 左侧 Examples 是概念的一个属性条目，用词语、对象或现实现象的名称帮助理解抽象概念，内容可为 `English 中文, English 中文, 中文词语`；右侧例子承担对左侧概念的完整讲解。具体见[Examples 左右分工](references/notion-note-steward/workflow.md#examples-的左右分工)
- 重要公式放在第五级原生罗马数字列表条目中；加粗双语标题后换行，正文第一行只放一个 inline equation `$\boxed{...}$`，只保留一个框，框内仅放核心形式化表达。符号、条件、含义和逻辑从正文第二行开始解释；详见[公式书写规范](references/notion-note-steward/workflow.md#公式条目的三行排版)
- 同一 H3 下尚未分组的第五级条目超过 6 个（7 个及以上）时，开始考虑按内容关系增加 H4 分组；这是考虑时机，不自动拆分。已有分组与用户布局继续保留
- 第五级在知识层级上承担最小知识单元的标题作用，使用原生小写罗马数字有序列表，不创建 H5；可以解释上级概念的属性，也可以直接承载独立术语。先写加粗双语标签并换行，再解释其全称与含义；Definition 在绝大多数概念中适用且通常优先，是否单列按实际内容判断，其他角度按需要选择，形式化定义通常用于数学学科
- 具体执行以[章节架构规则](references/notion-note-steward/workflow.md#章节架构与右侧辅助区)和[第五级语义规则](references/notion-note-steward/workflow.md#第五级的知识单元与解释角度)为准；数量和词数是优先范围，不为凑数删减有效知识，也不因本次 Skill 更新重排历史页面

按当前任务选择模块：只做封面不扩展为正文整理，只改公式不自动生成插图；同时涉及多项时读取对应模块。原有主题色、标题、画幅、裁切、已选版本、资源保留和实际显示检查要求继续适用。

执行前确认真实对象、页面身份、路径和授权范围。“方案”提供可审阅的只读稿；明确执行时承接同一对象和已确认要求。修改 Skill 文本本身只更新工作流文件。

用户当前明确指令优先。既有规范存在影响当前任务的冲突时，指出具体差异并提出建议，只确认受影响的选择，其余已授权工作继续完成。已确认的新规则应同步到相关模块，避免重复澄清。规范差异的历史记录见[原文差异说明](../../references/migration-notes.md)。

区分提示词、生成图片、上传素材和应用到页面。生成或导出不等于已应用；写入后分别核对内容、资源与实际显示，保留现有封面及用户已采用的版本。

行业或公司笔记及其封面、Logo 归[行业笔记](../industry-notes/SKILL.md)；个人博客、抖音或小红书作品的选题、改编、制作和管理归[创作管理](../creative-management/SKILL.md)。用户要求教学时使用[学习管理](../learning-management/SKILL.md)。已有笔记可以在获准范围内作为作品底稿，平台改编不自动写回原笔记或公开发布。

旧名称和现址见[完整索引](../../references/skill-map.md)。原文中的历史维护路径与旧调用名按索引定位，不写回已迁出的目录。
