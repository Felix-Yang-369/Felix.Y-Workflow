# Felix 工作流

这是 Felix 维护个人 Skills 的私人仓库。`plugins/felix-workflows/` 是唯一维护原件；每台设备安装后产生的 Codex 缓存不是编辑位置。

## 当前内容

| Skill | 用途 | 使用范围 |
| --- | --- | --- |
| 学科笔记 `$notion-note-steward` | 按知识树规范整理学科笔记，保留内容、层级和属性 | 学科页面 |
| 行业笔记 `$notion-industry-steward` | 按行业 Wiki 的现有层级整理行业、细分行业和企业研究 | 行业页面与企业研究 |
| 学科封面 `$secondary-discipline-cover` | 为学科页面设计系列封面；工程图解海报可沿用四张参考图 | 学科封面 |
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
    notion-note-steward/
    notion-industry-steward/
    notion-cover-designer/
    secondary-discipline-cover/
    company-logo/
    course-evaluation/
    schedule-management/
    abstract-knowledge-explainer/
    concrete-knowledge-explainer/
```

每个 Skill 的主要规则在自己的 `SKILL.md`；详细规则、模板和参考图在同目录的 `references/`、`assets/`；界面名称、独立图标和主题色在 `agents/openai.yaml`。修改时保留这些相对路径。

**命名约定：**`skills/` 下的目录名和 `SKILL.md` 中的 `name` 保持英文短名，便于跨设备安装和用 `$name` 调用；`agents/openai.yaml` 的 `interface.display_name` 使用中文或中英双语。界面上显示「学科笔记、行业笔记、学科封面、行业封面、公司 Logo」，技术标识继续沿用已有名称。

插件图标在 `assets/icon.svg`，两个插件清单都引用同一文件。它是原创的开卷与连接点图形；修改图标后更新清单中的路径并在小尺寸下检查辨识度。

每项 Skill 也有独立的 `assets/icon.svg`。`agents/openai.yaml` 的 `icon_small`、`icon_large` 指向该文件，`brand_color` 设置界面强调色。九个图标使用不同的底色和适合小尺寸识别的粗线条图形。

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
