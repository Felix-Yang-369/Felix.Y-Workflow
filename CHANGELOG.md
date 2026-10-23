# Changelog

[English README](README.md) · [中文首页](README.zh-CN.md)

Version notes preserved from the previous README. The 0.4.21 entry describes local source changes; its presence here does not assert that a GitHub release has been published.

以下版本说明从旧首页完整迁入；0.4.21 为本地源码说明，此记录不代表已发布 GitHub Release。

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

在学科笔记 Skill 中新增[数学概念的解释规范](plugins/felix-workflows/skills/knowledge-management/references/notion-note-steward/workflow.md#数学概念的解释规范)：Definition 使用固定双语句式, 适用的 Formal Definition 写明前提并框选公式, 其余讲解角度按需选择；附单态射示例与行为验收案例。规则更新不自动修改历史 Notion 页面。

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

- 学科、行业和公司笔记统一读取[完整覆盖与完成标准](plugins/felix-workflows/skills/knowledge-management/references/notion-note-steward/references/completion-workflow.md)，完整检查指定范围，按质量补齐，分批执行到完成。
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
