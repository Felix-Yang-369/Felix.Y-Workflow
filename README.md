# Felix 工作流

这是 Felix 维护个人 Skills 的私人仓库。`plugins/felix-workflows/` 是唯一维护原件；每台设备安装后产生的 Codex 缓存不是编辑位置。

## 当前内容

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
```

每个 Skill 的主要规则在自己的 `SKILL.md`；详细规则、模板和参考图在同目录的 `references/`、`assets/`；界面名称、独立图标和主题色在 `agents/openai.yaml`。修改时保留这些相对路径。

学科知识库的可编辑规范原件为 [SKILL.md](plugins/felix-workflows/skills/notion-academic-database-manager/SKILL.md)。保存修改后刷新或重新安装本机插件，并在新会话使用更新；源文件保存不代表当前对话实时热更新，也不会自动修改 Notion。

**命名约定：**`skills/` 下的目录名和 `SKILL.md` 中的 `name` 保持英文短名，便于跨设备安装和用 `$name` 调用；`agents/openai.yaml` 的 `interface.display_name` 使用中文或中英双语。界面上显示「学科笔记、行业笔记、学科封面、行业封面、公司 Logo」，技术标识继续沿用已有名称。

插件图标在 `assets/icon.svg`，两个插件清单都引用同一文件。它是原创的开卷与连接点图形；修改图标后更新清单中的路径并在小尺寸下检查辨识度。

每项 Skill 也有独立的 `assets/icon.svg`。`agents/openai.yaml` 的 `icon_small`、`icon_large` 指向该文件，`brand_color` 设置界面强调色。七个图标使用不同的鲜明底色和适合小尺寸识别的粗线条图形：书本、工厂、学科画框、行业画框、品牌徽记、勾选卡片和日历。

![七项 Skill 的图标预览](plugins/felix-workflows/assets/skill-icons-preview.png)

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

## 行业与公司规则拆分审核

2026-10-03 拆分稿已保存至源码，尚未刷新安装或发布。审核 [行业规则](plugins/felix-workflows/skills/notion-industry-steward/SKILL.md) 与 [公司规则](plugins/felix-workflows/skills/notion-company-steward/SKILL.md)。本轮标准为简短概览与现有属性补全，独立子公司页逐一审核后再考虑合并。规则审核后用于全量公司页任务。
