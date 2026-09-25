# Felix 工作流

这是 Felix 维护个人 Skills 的私人仓库。`plugins/felix-workflows/` 是唯一维护原件；每台设备安装后产生的 Codex 缓存不是编辑位置。

## 当前内容

| Skill | 用途 | 使用范围 |
| --- | --- | --- |
| `notion-note-steward` | 按既有规范整理 Notion 笔记，保留内容、层级和属性 | 笔记阅读、创建和编辑 |
| `notion-cover-designer` | 为需要封面的 Notion 页面搜索、生成和应用封面 | 封面任务 |
| `secondary-discipline-cover` | 按四张参考图的视觉语言设计二级学科系列封面提示词 | 指定海报风格时 |
| `course-evaluation` | 综合课程目录、教学大纲、软件与教师评价，形成有证据的选课建议 | 课程研究与比较 |
| `schedule-management` | 按权威来源核对和维护 Apple Calendar 的课程、考试、周次与节假日 | 学期日程管理 |

每项工作保留为独立 Skill。二级学科封面可为封面设计提供风格参考；仅在用户要求出图时生成图片，仅在用户要求应用到 Notion 时更改页面。封面设计师通常不在图内放文字，二级学科海报需要准确标题时应明确提出并检查成品。

## 仓库结构

```text
.agents/plugins/marketplace.json       本仓库的插件目录
plugins/felix-workflows/
  plugin.json                           插件信息（通用格式）
  .codex-plugin/plugin.json             旧版 Codex 兼容信息
  skills/
    notion-note-steward/
    notion-cover-designer/
    secondary-discipline-cover/
    course-evaluation/
    schedule-management/
```

每个 Skill 的主要规则在自己的 `SKILL.md`；详细规则、模板和参考图在同目录的 `references/`、`assets/`；界面名称在 `agents/openai.yaml`。修改时保留这些相对路径。

## 在另一台电脑使用

1. 从 GitHub 克隆这个私人仓库。Mac 可用 GitHub Desktop，或在终端运行 `git clone https://github.com/Felix-Yang-369/felix-workflows.git`。需要有访问此私人仓库的 GitHub 账号。
2. 在已安装 Codex 命令行工具的终端，进入仓库目录，运行：

   ```sh
   codex plugin marketplace add .
   codex plugin add felix-workflows@felix-workflows
   ```

3. 打开新的 Codex 对话，在 Plugins 中确认「Felix 工作流」已安装。可在任务中点名 `$notion-note-steward`、`$notion-cover-designer`、`$secondary-discipline-cover`、`$course-evaluation` 或 `$schedule-management`。安装使技能可用，并不表示每条消息都会调用全部技能。

如果 Mac 上已有同名的独立 Skill 或旧插件，先确认新插件可用，再停用旧安装，以免技能列表出现重复名称。不要从 `.codex/plugins/cache/` 复制或编辑安装副本。

## 编辑与接力

1. 先从 GitHub 拉取最新版本，再编辑本仓库 `plugins/felix-workflows/skills/<skill-name>/` 下的文件。
2. 新增 Skill 时，创建 `skills/<new-skill-name>/SKILL.md`，在文件开头写 `name` 和清楚的 `description`；把它用到的参考资料放在同一 Skill 目录内，避免依赖某台设备的绝对路径。
3. 检查改动后提交并推送到 GitHub。另一台电脑拉取更新，刷新或重新安装插件，然后在新对话中验证。
4. 不把账号凭据、Notion 本地数据库、生成缓存或设备专用配置提交到仓库。

本仓库保存工作流说明和参考资源，不包含 Notion 页面数据，也不自动连接 Notion。实际读写页面仍需相应连接和用户授权。
