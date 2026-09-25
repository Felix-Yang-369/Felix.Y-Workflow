# iCloud 学术日历管理规范

此文件随 `schedule-management` Skill 分发，是跨设备使用的规范原件。

版本：1.5
最后更新：2026-09-24
默认时区：`America/Los_Angeles`

## 1. 目的与适用范围

本文件是 Felix Yang 的 iCloud 学术日历管理规范。macOS 默认使用 Apple Calendar，Windows 使用已连接 iCloud 的 Notion Calendar；两端维护的是同一组 iCloud 日历。任何 agent 在读取、创建、修改或核对课程、考试、讨论课、学期周次、节假日和校园活动时，都应遵循本文件。

执行入口：本 Skill 的 `SKILL.md`（显示名称：`日程管理 SKILL`）。

目标：

- 标题简洁，分类依靠日历颜色表达。
- 同一课程在课程、讨论课和考试日历中使用同一个标准课程名。
- Week、节假日和考试信息可快速扫描。
- 所有写入操作可核对、可追踪、避免重复。

## 2. 信息来源优先级

发生冲突时，按以下顺序确定事实：

1. 课程 syllabus、教授公告、Canvas 课程页面。
2. UC Davis Schedule Builder 中当前注册的 section、时间和地点。
3. UC Davis Registrar Academic Calendar。
4. 邮件、聊天记录或用户口头补充。

用户最新的明确更正始终优先。若考试日期、考试形式、地点或 recurring scope 无法确认，先询问用户，不得猜测。

## 3. 日历分类

| iCloud 日历名称 | 用途 | 标题规则 |
|---|---|---|
| `专业课` | 正式 lecture / 主课程 | 仅使用标准课程名 |
| `水课` | 仅用于用户明确指定为该分类的课程 | 不由 agent 自行判断 |
| `讨论` | Discussion / discussion section | 仅使用标准课程名，不加 `Discussion` |
| `考试` | Midterm、Final、明确的考试安排 | 标准课程名 + 考试类型 |
| `活动` | Math Lab、讲座、社交活动、非考试会议 | 使用活动的正式名称 |
| `健身` | 锻炼、运动安排 | 使用简洁活动名称 |
| `标记` | Week 1–10、Final Week 等学期结构标记 | 使用本文件规定的精确标题 |
| `节假日` | 校历节假日和停课日 | 仅使用节日正式名称，不加分类前缀 |

不要把新的学期事件写入 `US Holidays`、`Holidays in United States` 或其他订阅日历。订阅日历只作为参考。

## 4. 标准课程名称

```yaml
courses:
  ECS_50: "ECS 50 Computer Organizations"
  ECS_171: "ECS 171 Machine Learning"
  MAT_150A: "MAT 150A Abstract Algebra"
  MAT_167: "MAT 167 Applied Linear Algebra"
  PHI_012: "PHI 12 Symbolic Logic"
```

课程事件和讨论课事件使用完全相同的标题，通过 `专业课` 与 `讨论` 的颜色区分。例如：

- Lecture：`ECS 50 Computer Organizations`，日历为 `专业课`。
- Discussion：`ECS 50 Computer Organizations`，日历为 `讨论`。

禁止使用以下冗余形式：

- `ECS 50 Computer Organizations Discussion`
- `Discussion — ECS 50 Computer Organizations`
- `ECS 50`（除非用户明确要求简称）

## 5. 考试命名

```yaml
exam_titles:
  numbered_midterm: "{course_name} Midterm {number}"
  single_midterm: "{course_name} Midterm Exam"
  final: "{course_name} Final"
calendar: "考试"
```

示例：

- `ECS 50 Computer Organizations Midterm 1`
- `MAT 150A Abstract Algebra Final`

Final 标题只在课程标准名末尾添加 `Final`，不得写成 `Final Exam`。

只要已确认 Midterm，就表示它替代该课程对应时段的 Lecture。日历中保留 `考试` 里的 Midterm，并移除同一课程、同一课堂时段的 Lecture occurrence，禁止两者重复显示。

考试时间和地点必须来自 syllabus、Canvas、教授公告或 Registrar 的可验证信息。不得用 lecture 时间推断考试时间，除非 syllabus 明确说明考试在课堂内进行。

若考试日期仍为 `TBA`，不得创建看似已确认的日历事件；应报告为待确认并在来源更新后补录。

## 6. Fall 2026 Week 标注

所有 Week 标注均为 `标记` 日历中的全天事件，位于每周一的 all-day 区域。标题必须完全匹配，不添加 `all day`、日期、句号或其他说明。

| 日期 | 标题 |
|---|---|
| 2026-09-28 | `Week 1` |
| 2026-10-05 | `Week 2` |
| 2026-10-12 | `Week 3` |
| 2026-10-19 | `Week 4` |
| 2026-10-26 | `Week 5` |
| 2026-11-02 | `Week 6` |
| 2026-11-09 | `Week 7` |
| 2026-11-16 | `Week 8` |
| 2026-11-23 | `Week 9` |
| 2026-11-30 | `Week 10` |
| 2026-12-07 | `Final Week` |

2026-09-23 至 2026-09-27 为 Week 0，不创建 `Week 0` 全天标记。Week 标记只表达学期结构，不代表所有 Discussion 都在该周开课；第一周是否有 Discussion 必须以课程公告或 syllabus 为准。

## 7. Fall 2026 节假日标注

节假日均为 `节假日` 日历中的全天事件。使用正式名称，不添加 `Holiday —` 等分类前缀。

| 日期 | 标题 |
|---|---|
| 2026-11-11 | `Veterans Day` |
| 2026-11-26 | `Thanksgiving Day` |
| 2026-11-27 | `Thanksgiving Holiday` |

`Holiday` 如果本身属于学校公布的正式名称（如 `Thanksgiving Holiday`），应保留；只移除人为添加的分类前缀。

官方节假日当天的 lecture 与 discussion 一律取消/移除，只保留 `节假日` 日历中的全天节日标签。考试、补课或特殊活动不得仅凭此规则取消，必须有课程或学校的明确来源。

## 8. Week 0 与 Week 10 完整性

- Week 0：课程 lecture 可从 Registrar 的 instruction start 开始，但 Discussion 的首日必须按各课来源单独确定，不能仅凭 recurring weekday 自动回填。Fall 2026 的首个有效 Discussion：ECS 50 为 2026-09-29；ECS 171、MAT 150A、PHI 12 均为 2026-10-01。PHI 12 教师明确通知第一周无 Discussion。任何落在星期六或早于对应首日的 Discussion 都视为异常，需核对并修正。
- Week 10：所有 lecture 与 discussion recurring series 必须覆盖到 Registrar 公布的最后教学日 2026-12-04；再按节假日和课程单独公告做例外。
- 核对时必须分别检查 Week 0、Week 10 和节假日，不能只看 recurrence 的首尾设置。

## 9. 活动命名

非课程、非考试的会议使用正式名称并归入 `活动`。例如：

```yaml
title: "Math Lab Introductory Meeting"
start: "2026-10-01T17:30:00-07:00"
end: "2026-10-01T18:30:00-07:00"
location: "MSB 1147, UC Davis"
notes: "Math Lab introductory meeting; logistics and Spring poster presentations."
calendar: "活动"
```

## 10. Agent 执行流程

每次处理日历任务时：

1. 读取本文件并确认当前学期、时区、执行客户端和目标 iCloud 日历；Windows 端另读 `notion-calendar-windows.md`。
2. 从权威来源提取课程、考试或校历信息；记录不确定项。
3. 先生成显式的学期 manifest；每个 lecture、discussion、lab family 都要记录 `first_date`、`last_date`、weekday、时间与地点，再按本文件规范化标题，不把分类词重复写入标题。
4. 用户说“今天好像少了”时，将其视为核对请求而不是确定更正：按 `America/Los_Angeles` 确定当天，列出所有 weekday 匹配的课程，再根据 `first_date`、`last_date`、节假日与课程公告区分“应有但缺失”和“本来不上课”。只有用户明确表示“今天照常上课”等确定信息时，才把它作为新更正覆盖旧来源。
5. 写入前以“标题 + 日期 + 时间 + 日历”检查是否已有事件，避免重复。
6. 对 recurring event，明确修改范围：单次、当前及以后、或整个系列。若用户意图不明确，先询问。
7. 保留已有 notes、location、URL、提醒和附件，除非用户明确要求修改。
8. 不删除事件，除非用户明确授权删除；优先修正已有事件。
9. 写入后先在当前客户端重新核对标题、日期、时间、全天状态、地点、日历分类和重复范围；等待同步后，在可用的另一客户端交叉核对。单独检查 Week 0、Week 10、每个节假日、每场考试，以及每个 Midterm 时段是否仍残留对应 Lecture。
10. 向用户报告完成项、因首周或停课规则而有意缺席的课程，以及仍需确认的任何信息。

## 11. 不确定性与冲突处理

以下情况必须先询问用户：

- syllabus 与 Canvas 或 Schedule Builder 的考试信息冲突。
- 无法判断修改应应用到单次事件还是整个 recurring series。
- 用户没有指定某门课属于 `专业课` 还是 `水课`。
- 课程名称、section、地点或考试时间只有推测，没有可靠来源。

以下情况可直接规范化：

- 从讨论课标题移除 `Discussion`，前提是事件仍保留在 `讨论` 日历。
- 从节日标题移除 `Holiday —` 分类前缀，前提是事件移入 `节假日` 日历。
- 将 Week 标题修正为第 6 节中的精确格式和日期。

## 12. 完成标准

日历维护任务只有在以下条件都满足时才算完成：

- 没有重复事件。
- 标题符合标准课程名或事件名。
- 分类日历正确。
- Week 与节假日处于 all-day 区域。
- 节假日当天没有 lecture 或 discussion。
- Midterm 时段没有同一课程的重复 Lecture。
- Final 标题以 `Final` 结尾，不含 `Final Exam`。
- Week 10 的有效课程持续到最后教学日。
- 日期、时间、地点和时区已核对。
- recurring 修改范围正确。
- 关键事件已在当前客户端主视图中重新检查；可访问另一同步客户端时，已完成交叉核对。
