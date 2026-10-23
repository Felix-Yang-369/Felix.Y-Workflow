# Previous README · 完整历史原文

This source snapshot preserves the README before the bilingual redesign. Statements about repository visibility, names, versions, and installation are historical; use the current README and guides for instructions.

以下以 Markdown 源码完整保留改版前首页；其中仓库可见性、名称、版本及安装说明属于历史记录，当前用法请以新首页和指南为准。

````markdown
# FELIX WORKFLOW

这是 Felix 维护个人 Skills 的私人仓库。`plugins/felix-workflows/` 是唯一维护原件；每台设备安装后产生的 Codex 缓存不是编辑位置。

## 当前内容

0.4.21 本地版统一显示名为 `FELIX WORKFLOW`，插件图标采用个人网站提供的 FY 标识，主题色为 `#55786D`；保留现有十三项技能及已保存的公式、原生罗马数字列表和 Logo 视觉尺度修订。金融管理等扩展仍处于方案阶段。

0.4.20 统一概念的四级分组：性质独立为 H4 时, 前文同步使用 `I. Definition 定义`, 后接 `II. Properties 性质`；左侧 Examples 的数学符号加空格与对应名称, 如 `GL 一般线性群`。

0.4.19 按数学笔记样例反馈进一步精简形式化定义：默认一个核心公式与必要符号说明, 多条性质可独立 H4 并逐项有序列出, 左侧例子简写、右侧完整例子使用浅灰色 callout；保留概念区分与必要前提。

0.4.18 在学科笔记 Skill 中新增[数学概念的解释规范](plugins/felix-workflows/skills/notion-note-steward/SKILL.md#数学概念的解释规范)：Definition 使用固定双语句式, 适用的 Formal Definition 写明前提并框选公式, 其余讲解角度按需选择；附单态射示例与行为验收案例。规则更新不自动修改历史 Notion 页面。

| Skill | 用途 | 使用范围 |
| --- | --- | --- |
| 学科知识库管理规范 `$notion-academic-database-manager` | 统一三视图、Full Page 打开、卡片预览与核心字段，迁移属性并验收 | 学科数据库 |
| 学科笔记 `$notion-note-steward` | 按知识树规范整理学科笔记，保留内容、层级和属性 | 学科页面 |
| 学科插图 `$academic-illustration` | 选择实物图、局部标注、辅助示意或完整概念图，放在对应知识点右侧 | 学科正文插图 |
| 行业笔记 `$notion-industry-steward` | 维护行业分类、层级、行业分析与比较资料 | 行业与细分行业页面 |
| 公司笔记 `$notion-company-steward` | 优化公司概览、现有属性与母子公司关系 | 公司与集团页面 |
| 学科封面 `$secondary-discipline-cover` | 为学科页面设计系列封面；工程图解海报可沿用四张参考图 | 学科封面 |
| 写实风格学科封面 `$photorealistic-discipline-cover` | 以真实照片或场景生成电影感封面，左上角英文大写标题，默认 16:9 | 写实学科封面与照片改编 |
| 行业封面 `$notion-cover-designer` | 为行业页面搜索、生成和应用风格连贯的封面 | 行业封面 |
| 公司 Logo `$company-logo` | 优先选用官方现成图，否则参考官方素材生成品牌色背景的 16:9 Logo 横图；也支持方形图标和明确要求的原创设计 | 公司研究页面封面、页面图标或原创品牌设计 |
| `course-evaluation` | 综合课程目录、教学大纲、软件与教师评价，形成有证据的选课建议 | 课程研究与比较 |
| `schedule-management` | 按权威来源，通过 macOS Apple Calendar 或 Windows Notion Calendar 维护同一组 iCloud 课程、考试、周次与节假日 | 跨设备学期日程管理 |
| 抽象知识讲解 `$abstract-knowledge-explainer` | 从具体问题和旧知识出发，逐步建立抽象概念、正式定义与直觉 | 抽象代数、信息论、计算理论、拓扑、理论机器学习 |
| 具象知识讲解 `$concrete-knowledge-explainer` | 用结构与动态流程图解系统，再解释原理、模型和失效情况 | 机械工程、电路、硬件、机器人、制造 |

Notion 相关的五项在技能列表里使用中文名称，不以「Notion」开头。英文目录名和 `$name` 是稳定的调用标识，暂不改动现有标识，以免旧提示词失效。学科封面仅在用户要求出图时生成图片，仅在用户要求应用到页面时更改页面；行业封面保留已有封面，除非用户要求更换。公司 Logo 默认指现有公司的官方标识制作的横向展示图，不代表重新设计其品牌。

## 仓库结构

```text
.agents/plugins/marketplace.json       本仓库的插件目录
plugins/felix-workflows/
  plugin.json                           插件信息（通用格式）
  .codex-plugin/plugin.json             旧版 Codex 兼容信息
  assets/icon.svg                      插件图标
  skills/
    notion-academic-database-manager/
    notion-note-steward/
    academic-illustration/
    notion-industry-steward/
    notion-company-steward/
    notion-cover-designer/
    secondary-discipline-cover/
    photorealistic-discipline-cover/
    company-logo/
    course-evaluation/
    schedule-management/
    abstract-knowledge-explainer/
    concrete-knowledge-explainer/
```

每个 Skill 的主要规则在自己的 `SKILL.md`；详细规则、模板和参考图在同目录的 `references/`、`assets/`；界面名称、独立图标和主题色在 `agents/openai.yaml`。修改时保留这些相对路径。

学科知识库的可编辑规范原件为 [SKILL.md](plugins/felix-workflows/skills/notion-academic-database-manager/SKILL.md)。保存修改后刷新或重新安装本机插件，并在新会话使用更新；源文件保存不代表当前对话实时热更新，也不会自动修改 Notion。

**命名约定：**`skills/` 下的目录名和 `SKILL.md` 中的 `name` 保持英文短名，便于跨设备安装和用 `$name` 调用；`agents/openai.yaml` 的 `interface.display_name` 使用中文或中英双语。界面上显示「学科笔记、行业笔记、学科封面、行业封面、公司 Logo」，技术标识继续沿用已有名称。

插件图标在 `assets/icon.svg`，两个插件清单都引用同一文件。当前采用 Felix 提供的个人网站 FY 标识，使用绿色底与浅色字形；修改图标后在小尺寸及浅深背景下检查辨识度。

多数 Skill 配有独立的 `assets/icon.svg`。`agents/openai.yaml` 的 `icon_small`、`icon_large` 指向该文件，`brand_color` 设置界面强调色。图标使用不同的底色和适合小尺寸识别的粗线条图形；未配置图标的技能仍可正常使用。

原有七项 Skill 的图标预览：![原有七项 Skill 的图标预览](plugins/felix-workflows/assets/skill-icons-preview.png)。新增的两个图标分别用汇聚的节点和相连的部件表达抽象与具象讲解。

抽象知识讲解适合“概念本身难以看见”的问题，依次解释现实问题、动机、旧方法的困难、与已知概念的关系、抽象过程、正式定义，再检查直觉。具象知识讲解适合“系统如何构造和运作”的问题，依次展示结构、部件、运动或信息/能量/受力流程、原理、数学模型及应用与失效。两者可按主题混用，不必机械套用全部步骤。

`schedule-management` 以 iCloud 日历为共享数据层：macOS 默认操作 Apple Calendar，Windows 操作已连接 iCloud 的 Notion Calendar。Notion 数据库日历不是这些课程日历的替代品；跨客户端写入后需要等待同步并检查重复事件。

## 在另一台电脑使用

1. 从 GitHub 克隆这个私人仓库。Mac 可用 GitHub Desktop，或在终端运行 `git clone https://github.com/Felix-Yang-369/felix-workflows.git`。需要有访问此私人仓库的 GitHub 账号。
2. 在已安装 Codex 命令行工具的终端，进入仓库目录，运行：

   ```sh
   codex plugin marketplace add .
   codex plugin add felix-workflows@felix-workflows
   ```

3. 打开新的 Codex 对话，在 Plugins 中确认「Felix 工作流」已安装。可在任务中点名上表中的 `$name`。安装使技能可用，并不表示每条消息都会调用全部技能。

如果 Mac 上已有同名的独立 Skill 或旧插件，先确认新插件可用，再停用旧安装，以免技能列表出现重复名称。不要从 `.codex/plugins/cache/` 复制或编辑安装副本。

## 编辑与接力

1. 先从 GitHub 拉取最新版本，再编辑本仓库 `plugins/felix-workflows/skills/<skill-name>/` 下的文件。
2. 新增 Skill 时，创建 `skills/<new-skill-name>/SKILL.md`，在文件开头写 `name` 和清楚的 `description`；把它用到的参考资料放在同一 Skill 目录内，避免依赖某台设备的绝对路径。
3. 检查改动后提交并推送到 GitHub。另一台电脑拉取更新，刷新或重新安装插件，然后在新对话中验证。
4. 不把账号凭据、Notion 本地数据库、生成缓存或设备专用配置提交到仓库。

本仓库保存工作流说明和参考资源，不包含 Notion 页面数据，也不自动连接 Notion。实际读写页面仍需相应连接和用户授权。

## 0.4.6：执行范围与连续工作

- 学科笔记区分方案分析、内容完善、排版整理和结构重整；学科 INTRODUCTION 不编号，保留已有工作区身份验证与左右栏规则。
- 两项讲解技能区分首次讲解与局部追问，在当前对话中保留主线和待探索问题，按问题切换抽象与具象方法。
- 学科封面以已认可系列为先，局部修改保持其他已认可内容，并同步检查提示词模板与裁切。
- 更新后使用 [行为验收案例](docs/skill-acceptance.md) 检查；静态文件检查不等于模型在真实会话中的行为测试。

升级时先比较同名独立 Skill 的全部文件，保留独有内容或说明已被较新规则替代；备份后仅停用已由插件覆盖的独立副本。发布后刷新市场、重新安装并核对实际缓存文件与源文件一致。旧会话可能仍持有旧技能说明，需在新会话验证。

## 0.4.13：最新工作流同步

- 合并本地最新的学科数据库管理、学科插图、公司笔记和写实学科封面技能，与仓库已有的抽象、具象知识讲解技能；共十三项技能。
- 保留远端的执行范围、连续讲解与局部封面修改规则，更新学科父页顺序、学习进度维护边界及学科封面参考资源。
- 行业与公司规则已拆分发布；发布技能规则本身不执行 Notion 页面或数据库操作。

## 分享给好友

这是私人仓库，好友需先接受 GitHub 仓库访问邀请，并在自己的电脑上配置 GitHub 访问权限。安装了 Codex 命令行工具后，可直接运行：

```sh
codex plugin marketplace add Felix-Yang-369/felix-workflows
codex plugin add felix-workflows@felix-workflows
```

重启 Codex 后开启新对话，在 Plugins 中确认「Felix 工作流」。好友需要自行连接 Notion、日历等服务；这些工作流包含 Felix 的个人页面结构与格式约定，在其他工作区使用时应明确目标与适用规则，不自动套用 Felix 的页面 ID 或日历配置。

已安装用户可运行以下命令获取更新，再重启并开启新对话：

```sh
codex plugin marketplace upgrade felix-workflows
codex plugin add felix-workflows@felix-workflows
```

## 0.4.14：完整覆盖、内容深度与完成验收

- 学科、行业和公司笔记统一读取[完整覆盖与完成标准](plugins/felix-workflows/skills/notion-note-steward/references/completion-workflow.md)，完整检查指定范围，按质量补齐，分批执行到完成。
- 承接已接受方案，交付前检查遗漏与前后一致性，分别报告内容回读和视觉验收；保留只读建议、局部任务及公司简短概览边界。
- 合并本机已有的右侧学科联系、60:40 双栏、H1 全宽与流程图 Display 规则，保留 0.4.13 的父页模板、学习进度和十三项技能。
- 增加整篇、整库、局部、写入失败和视觉受限等验收场景。静态检查不保证每次模型输出都达标，后续真实使用仍需按覆盖清单验收。

## 0.4.15：默认逐项验收

学科、行业与公司笔记默认执行“本次授权范围内全部页面逐项验收，有缺口继续处理，最后列出实际未完成项”。三项技能入口、默认提示词及共享完成规则同步更新；没有剩余时也明确写无，未验证项不计作全部完成。保持局部任务与只读方案边界。

## 0.4.16：要求继承、返工诊断与双重验收

- 三项笔记技能继承已确认要求，局部修正只覆盖对应事项，保留准确标题、位置与排除项。
- 返工先区分遗漏、深度、结构、显示、写入失败和新增需求，再修复并检查同范围的同类问题。
- 结构与内容分别验收，视觉检查独立记录；学科示例就近组织，完整格式整理检查适用的第五层有序列表。保留局部、只读与公司简短概览边界。

## 0.4.17：一流教材与讲义参考

- 学科正文新建、补充和深化时，优先参考适合当前层次的领域公认教材与官方课程讲义，实际核实相关章节的定义、条件、推导、例题与边界。
- 区分书目核实与正文阅读，用自己的语言组织内容；时变知识另核对现行权威资料，仅使用免费或已有权限的资源。
- 保留既有架构与格式整理边界，默认不往 Notion 正文添加书目或引用；交付回复简要说明实际依据和待核实项。
````
