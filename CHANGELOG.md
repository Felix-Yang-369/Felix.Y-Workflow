# Changelog

[English README](README.md) · [中文首页](README.zh-CN.md)

Version notes preserved from the previous README. The 0.4.21 entry describes local source changes; its presence here does not assert that a GitHub release has been published.

以下版本说明从旧首页完整迁入；0.4.21 为本地源码说明，此记录不代表已发布 GitHub Release。

## 0.5.2 · Academic-note formulas, columns, and supporting content · 2026-10-24

- 重要公式使用 inline equation，在第五级原生罗马数字条目中按“标题行 → 正文第一行单个 `oxed{}` 公式 → 正文第二行起解释”书写。公式框内只保留核心形式化表达，名称、释义和推导逻辑放在下方；同步清理示例中的框内解释文字。
- 新建正文双栏默认以左侧 H3 为起点，H3、H4 及所属正文留在同一左栏，右侧辅助内容从同组顶部并列开始；导论仍由 H2 Overview 与当前封面并列。已有分组、比例和用户布局保留。
- 左侧 Examples 是概念的一个属性条目，以词语、名称或现实现象建立直观联系；各项用半角逗号加空格分隔，双语词语内部用空格。右侧例子承担完整讲解，不按文字长短互换职责。
- 同一 H3 下尚未分组的第五级条目超过六个时开始考虑 H4 分组，不自动拆分，也不因已有组内数量较少而撤销分组。
- 取消“通常两至四个解释角度”的数量倾向，改为按概念实际需要选择、合并重复内容，保留有独立职责的角度。
- Connections 优先在 INTRODUCTION 右侧封面下方按需出现一处；其他章节仅在有独特理解价值时少量添加，不以每章一次为目标。
- 笔记插图不添加来源标签或段落；只有单看图意不清时补一行简短解释，图内已有讲解时不再补外部说明。图片内容准确性仍按既有规则核对。
- 同步中英文 README、安装说明、版本元数据与静态验收场景，保留全部其他工作流、素材及已保存规则。新会话行为和业务页面视觉显示仍按实际任务另行核验。

## 0.5.1 · Academic notes and six-domain architecture · 2026-10-23

- 一级入口前两位改为学科笔记 `$academic-notes`、行业笔记 `$industry-notes`；后续为金融、日程、学习、创作。
- 学科图解封面和写实封面归学科笔记；行业封面与公司 Logo 归行业笔记，模块、模板和资源完整迁移。创作管理负责个人博客、抖音和小红书作品，各有独立 Markdown。
- 保留用户发布 0.5.0 后的企业字段手动修改、其他现有规则与资源；旧入口、清单、索引和改写前文档留档，不使用旧缓存覆盖维护源码。迁移哈希记录初迁快照，后续规则以当前模块为准。
- 学科笔记限定为 Notion 学科知识库，按任务读取完整模块；一级实质章节优先 4–7 章、以 5–6 章为佳，英文命名优先 1–4 词、以 2–3 词为佳。H1 英文独立单词 `and` 不区分大小写统一写为 `&`。
- 固定导论开头为 INTRODUCTION 导论 → A. Overview → a. Definition，下接原生小写罗马数字列表 Definition、Position。首项固定为“简称, 全称, 解释”，无通行简称时写“全称, 解释”，分隔为半角逗号加一个空格。Position 按需简述上级归属、相邻边界和体系作用。
- Core Questions 按需作为 Position 后的第五级列表项；起源或历史仅在一级学科确有需要时考虑，末端专题笔记不默认添加。移除重复的 Related Disciplines 章节示例，详细学科联系继续使用右侧 Connections。
- 导论固定 Overview 左、当前学科封面右，H1 在双栏外；新建双栏默认 6:4，可选 5:5 或 7:3。保留已有比例和用户手动布局，约 5 行只作视觉参考，不自动触发重排，知识单元完整与图文对应优先。
- 普通知识条目的 Definition 默认优先、按实际内容判断；第五级继续使用原生罗马数字列表承载属性解释或最小术语，Formal Definition 通常用于数学，不强制给每个概念套满属性。
- 学科数据库默认视图统一为学科概览 Gallery、学科信息 Table。分类字段统一为学科分支，保留选项与字段类型；学科层级仅表示层级编号，角色信息另行保留，不自动转换或合并；移除学科成绩相关要求。
- 已授权数据库维护仅将空白学习进度初始化为 0%，已有值不动、不估算。学科难度以 Felix 个人学习感受为准；新建时默认继承直属上级难度，上级未填则留空，已有评级不动。
- 学科主题色不设默认占位选项；新建或获准补填空白时，可依据已有背景色或学科相关元素先选九种颜色之一，保留已有值及用户手动修正。Gallery 卡片隐藏该字段，Table 和打开的笔记页面显示。
- 更新中英文 README、安装说明与验收案例，同步 GitHub 源码和本地安装。入口顺序由索引与文档表达，宿主列表排序由界面控制；新会话真实行为及业务页面视觉显示仍按实际任务另行验证。

## 0.5.0 · Six editable domain entries · 2026-10-23

- Expose Knowledge, Finance, Planning, Learning, Research, and Creative as six callable Skills.
- Preserve all 13 original workflows, supporting Markdown, UI metadata, icons, and examples as complete independently editable modules; retain the latest user-saved academic database rules and their existing unresolved conflicts.
- Add cash-flow reconciliation and portfolio review methods, shared execution rules, an old-name map, and a file-by-file preservation manifest.
- Keep the stable plugin ID and FY branding. Update both READMEs, the module catalog, customization, and installation instructions for GitHub and editable local sources.
- Preserve the previous documentation in full under [pre-publication source](docs/preserved/README.md). Static checks cover six entries, 65 original files, links, and source/cache equality; real account operations and business-page visual checks are not part of this release verification.

六类入口、13 个原工作流全文与全部配套文件完整保留；金融新增两份方法规范。最新手动修改原样保留，本轮不删除或统一其规则。GitHub 源码同步、本机安装和真实业务行为分开核对；此更新记录不表示创建了单独的 GitHub Release。

## 0.4.21

本地版统一显示名为 `FELIX WORKFLOW`，插件图标采用个人网站提供的 FY 标识，主题色为 `#55786D`；保留现有十三项技能及已保存的公式、原生罗马数字列表和 Logo 视觉尺度修订。金融管理等扩展仍处于方案阶段。

## 0.4.20

统一概念的四级分组：性质独立为 H4 时, 前文同步使用 `I. Definition 定义`, 后接 `II. Properties 性质`；左侧 Examples 的数学符号加空格与对应名称, 如 `GL 一般线性群`。

## 0.4.19

按数学笔记样例反馈进一步精简形式化定义：默认一个核心公式与必要符号说明, 多条性质可独立 H4 并逐项有序列出, 左侧例子简写、右侧完整例子使用浅灰色 callout；保留概念区分与必要前提。

## 0.4.18

在学科笔记 Skill 中新增[数学概念的解释规范](plugins/felix-workflows/skills/academic-notes/references/notion-note-steward/workflow.md#数学概念的解释规范)：Definition 使用固定双语句式, 适用的 Formal Definition 写明前提并框选公式, 其余讲解角度按需选择；附单态射示例与行为验收案例。规则更新不自动修改历史 Notion 页面。

## 0.4.17 — 一流教材与讲义参考

- 学科正文新建、补充和深化时，优先参考适合当前层次的领域公认教材与官方课程讲义，实际核实相关章节的定义、条件、推导、例题与边界。
- 区分书目核实与正文阅读，用自己的语言组织内容；时变知识另核对现行权威资料，仅使用免费或已有权限的资源。
- 保留既有架构与格式整理边界，默认不往 Notion 正文添加书目或引用；交付回复简要说明实际依据和待核实项。

## 0.4.16 — 要求继承、返工诊断与双重验收

- 三项笔记技能继承已确认要求，局部修正只覆盖对应事项，保留准确标题、位置与排除项。
- 返工先区分遗漏、深度、结构、显示、写入失败和新增需求，再修复并检查同范围的同类问题。
- 结构与内容分别验收，视觉检查独立记录；学科示例就近组织，完整格式整理检查适用的第五层有序列表。保留局部、只读与公司简短概览边界。

## 0.4.15 — 默认逐项验收

学科、行业与公司笔记默认执行“本次授权范围内全部页面逐项验收，有缺口继续处理，最后列出实际未完成项”。三项技能入口、默认提示词及共享完成规则同步更新；没有剩余时也明确写无，未验证项不计作全部完成。保持局部任务与只读方案边界。

## 0.4.14 — 完整覆盖、内容深度与完成验收

- 学科、行业和公司笔记统一读取[完整覆盖与完成标准](plugins/felix-workflows/skills/academic-notes/references/notion-note-steward/references/completion-workflow.md)，完整检查指定范围，按质量补齐，分批执行到完成。
- 承接已接受方案，交付前检查遗漏与前后一致性，分别报告内容回读和视觉验收；保留只读建议、局部任务及公司简短概览边界。
- 合并本机已有的右侧学科联系、60:40 双栏、H1 全宽与流程图 Display 规则，保留 0.4.13 的父页模板、学习进度和十三项技能。
- 增加整篇、整库、局部、写入失败和视觉受限等验收场景。静态检查不保证每次模型输出都达标，后续真实使用仍需按覆盖清单验收。

## 0.4.13 — 最新工作流同步

- 合并本地最新的学科数据库管理、学科插图、公司笔记和写实学科封面技能，与仓库已有的抽象、具象知识讲解技能；共十三项技能。
- 保留远端的执行范围、连续讲解与局部封面修改规则，更新学科父页顺序、学习进度维护边界及学科封面参考资源。
- 行业与公司规则已拆分发布；发布技能规则本身不执行 Notion 页面或数据库操作。

## 0.4.6 — 执行范围与连续工作

- 学科笔记区分方案分析、内容完善、排版整理和结构重整；学科 INTRODUCTION 不编号，保留已有工作区身份验证与左右栏规则。
- 两项讲解技能区分首次讲解与局部追问，在当前对话中保留主线和待探索问题，按问题切换抽象与具象方法。
- 学科封面以已认可系列为先，局部修改保持其他已认可内容，并同步检查提示词模板与裁切。
- 更新后使用 [行为验收案例](docs/skill-acceptance.md) 检查；静态文件检查不等于模型在真实会话中的行为测试。

升级时先比较同名独立 Skill 的全部文件，保留独有内容或说明已被较新规则替代；备份后仅停用已由插件覆盖的独立副本。发布后刷新市场、重新安装并核对实际缓存文件与源文件一致。旧会话可能仍持有旧技能说明，需在新会话验证。
