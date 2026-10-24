# 一级入口与独立模块索引

0.5.1 本地架构。下列顺序为维护导航顺序；宿主技能列表的最终排序由 Codex 界面决定。

| 顺序 | 一级入口 | 调用 | 职责 |
|---|---|---|---|
| 1 | [学科笔记](../skills/academic-notes/SKILL.md) | `$academic-notes` | 学科数据库、正文、插图、图解与写实学科封面 |
| 2 | [行业笔记](../skills/industry-notes/SKILL.md) | `$industry-notes` | 行业与公司笔记、企业属性、行业封面、公司 Logo |
| 3 | [金融管理](../skills/finance-management/SKILL.md) | `$finance-management` | 收支、对账与投资复盘 |
| 4 | [日程管理](../skills/schedule-management/SKILL.md) | `$schedule-management` | 课程、考试与日历 |
| 5 | [学习管理](../skills/learning-management/SKILL.md) | `$learning-management` | 抽象／具象讲解及课程评估 |
| 6 | [创作管理](../skills/creative-management/SKILL.md) | `$creative-management` | 个人博客、抖音与小红书作品 |

## 完整保留的原工作流

| 原工作流 | 当前入口 | 可独立编辑的全文 |
|---|---|---|
| `notion-academic-database-manager` | `$academic-notes` | [workflow.md](../skills/academic-notes/references/notion-academic-database-manager/workflow.md) |
| `notion-note-steward` | `$academic-notes` | [workflow.md](../skills/academic-notes/references/notion-note-steward/workflow.md) |
| `academic-illustration` | `$academic-notes` | [workflow.md](../skills/academic-notes/references/academic-illustration/workflow.md) |
| `secondary-discipline-cover` | `$academic-notes` | [workflow.md](../skills/academic-notes/references/secondary-discipline-cover/workflow.md) |
| `photorealistic-discipline-cover` | `$academic-notes` | [workflow.md](../skills/academic-notes/references/photorealistic-discipline-cover/workflow.md) |
| `notion-industry-steward` | `$industry-notes` | [workflow.md](../skills/industry-notes/references/notion-industry-steward/workflow.md) |
| `notion-company-steward` | `$industry-notes` | [workflow.md](../skills/industry-notes/references/notion-company-steward/workflow.md) |
| `notion-cover-designer` | `$industry-notes` | [workflow.md](../skills/industry-notes/references/notion-cover-designer/workflow.md) |
| `company-logo` | `$industry-notes` | [workflow.md](../skills/industry-notes/references/company-logo/workflow.md) |
| `schedule-management` | `$schedule-management` | [workflow.md](../skills/schedule-management/references/schedule-management/workflow.md) |
| `abstract-knowledge-explainer` | `$learning-management` | [workflow.md](../skills/learning-management/references/abstract-knowledge-explainer/workflow.md) |
| `concrete-knowledge-explainer` | `$learning-management` | [workflow.md](../skills/learning-management/references/concrete-knowledge-explainer/workflow.md) |
| `course-evaluation` | `$learning-management` | [workflow.md](../skills/learning-management/references/course-evaluation/workflow.md) |

## 个人作品与金融方法

- [个人博客](../skills/creative-management/references/personal-blog.md)
- [抖音作品](../skills/creative-management/references/douyin.md)
- [小红书作品](../skills/creative-management/references/xiaohongshu.md)
- [收支与对账](../skills/finance-management/references/cashflow.md)
- [投资复盘](../skills/finance-management/references/portfolio.md)

旧 `$knowledge-management` 对应当前 `$academic-notes`，旧 `$research-management` 对应当前 `$industry-notes`；这是名称导航，不是宿主原生别名。原四类视觉工作流现在分别归前两个入口。原模块中的旧维护路径和调用名按本表定位。

原入口、UI、清单与索引的完整文本保存在 references/architecture-history/0.5.0/，完整备份与逐文件对应见[本轮保留清单](architecture-migration.json)。历史副本不作为额外一级 Skill。
