# FELIX WORKFLOW 一级架构 · 0.5.1

| 顺序 | 一级入口 | 调用 | 职责 |
|---|---|---|---|
| 1 | [学科笔记](../plugins/felix-workflows/skills/academic-notes/SKILL.md) | `$academic-notes` | 学科数据库、正文、插图、图解与写实学科封面 |
| 2 | [行业笔记](../plugins/felix-workflows/skills/industry-notes/SKILL.md) | `$industry-notes` | 行业与公司笔记、企业属性、行业封面、公司 Logo |
| 3 | [金融管理](../plugins/felix-workflows/skills/finance-management/SKILL.md) | `$finance-management` | 收支、对账与投资复盘 |
| 4 | [日程管理](../plugins/felix-workflows/skills/schedule-management/SKILL.md) | `$schedule-management` | 课程、考试与日历 |
| 5 | [学习管理](../plugins/felix-workflows/skills/learning-management/SKILL.md) | `$learning-management` | 抽象／具象讲解及课程评估 |
| 6 | [创作管理](../plugins/felix-workflows/skills/creative-management/SKILL.md) | `$creative-management` | 个人博客、抖音与小红书作品 |

四个视觉模块与其参考、UI 和素材跟随对应笔记模块：学科封面、写实学科封面归学科笔记；行业封面和公司 Logo 归行业笔记。原学科插图继续归学科笔记。

创作管理负责个人博客、抖音和小红书作品的选题、原稿、脚本、素材、制作、版本、发布准备与复盘。笔记资料可以按需求作为底稿；改编、源笔记修改、公开发布是分别识别的任务。

[全部独立模块](workflows.md) · [直接编辑规则](customization.md) · [最新原文保留清单](../plugins/felix-workflows/references/architecture-migration.json) · [文档存档](preserved/README.md)

架构迁移时曾保留的学科数据库差异，已按用户后续逐条确认同步到当前规范，详见[规则确认记录](../plugins/felix-workflows/references/migration-notes.md)。企业字段规范的手动修改纳入基线并完整保留。旧名称只作为导航记录，不作为额外的宿主调用别名。

以上是维护索引与文档顺序，Codex 技能列表的最终排序由宿主控制。插件不添加未声明的排序字段。0.5.1 同步维护源码、GitHub 与本地安装；规则仍可直接在独立 Markdown 文件中编辑。迁移清单中的哈希记录捕获时的迁移快照，后续用户确认的规则修订以当前文件为准。
