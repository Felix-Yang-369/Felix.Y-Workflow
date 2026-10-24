# Felix.Y 的个人空间：学科笔记详细格式指南

本指南以 2026-08-20 观察到的习惯为基础，持续维护。使用时仍需检查当前同级页面，不应仅凭旧模板覆盖已有的明确结构。

## 通用格式速查

主文件 `SKILL.md` 维护通用规则；本节便于对照模板。修改标题、编号或标点规则时，应同步检查主文件，避免冲突。

| 项目 | 规则 |
|---|---|
| 页面与数据库名称 | `ENGLISH 中文`，英文全部大写；有通行简称时优先简称，否则用全称 |
| 全称解释 | 放在固定导论的 `INTRODUCTION → A. Overview → a. Definition → i. Definition`；写 `简称, 全称, 解释`，无通行简称时写 `全称, 解释`，分隔固定为半角逗号加一个空格，不堆入标题 |
| 名称示例 | `DS 数据科学`、`AI 人工智能`、`NLP 自然语言处理`、`MLOPS 模型运维`、`DATA ANALYSIS 数据分析` |
| 图标 | 同级页面使用 emoji 时，选择与分类相关的 emoji |
| 双语顺序 | 英文在前，中文在后 |
| 学科一级章节数量 | 不含 INTRODUCTION 的实质章节优先 4–7 章，以 5–6 章为佳；不机械套到每组下级标题，学科父页沿用专用顺序 |
| 学科章节命名 | 英文名称优先 1–4 个单词，以 2–3 个为佳；二三级标题优先描述学科本质、对象与内在结构，参考用户已有命名，不套固定章目 |
| H1（一个井号 `#`） | 大写罗马数字编号，如 `# I. TOPIC 主题:`；英文全大写，独立单词 and（不区分大小写）统一替换为 &，符号两侧各一个空格；文本背景色使用本笔记主题色；学科页始终位于双栏外 |
| H2（两个井号 `##`） | 大写字母编号，如 `## A. Topic 主题:`；英文采用标题式大小写（Title Case）；蓝色文字 |
| H3（三个井号 `###`） | 小写字母编号，如 `### a. Topic 主题:`；英文采用标题式大小写（Title Case）；橙色文字 |
| H4（四个井号 `####`） | 大写罗马数字编号，如 `#### I. Topic 主题:`；英文采用标题式大小写（Title Case）；黄色文字 |
| 第五级（通过有序列表实现） | 使用原生小写罗马数字有序列表 i、ii、iii，不创建 `#####` 或 H5；Notion MCP 使用 `<ol type="i">` 与 `<li>`，保留分组与嵌套 |
| 新增列表项 | `<li>` 内先写加粗双语标签与冒号，再软换行写解释；整个条目留在同一个编号列表块内 |
| 第五级语义 | 可解释 H3/H4 概念的属性，也可作为独立最小术语；术语标签换行后先解释规范全称与含义，不编造全称或别名 |
| 属性角度 | Definition 在绝大多数概念中适用且通常优先，是否单列按实际内容判断；Formal Definition 通常用于数学；Formula、Applications、Situations、Motivation、Properties、Intuition、Core Idea、Examples 等按需选择，不全部强制列齐 |
| 公式条目 | 同一个原生有序列表块内: 第一行加粗双语名称, 第二行行内 `$\boxed{...}$` 公式, 第三行起解释；三部分使用 `<br>` 或软换行连接 |
| 逗号 | 新写的笔记正文用半角 `,`，后续还有短语时加一个空格 |
| 句末标点 | 普通段落和解释性列表项末尾不加 `。` 或 `.`；保留代码、URL、引文、缩写、数据值和字面名称中的必要标点 |
| 引用 | 默认不添加参考资料、来源章节或行内引用，用户明确要求时才加入 |
| 流程图 | 默认仅展示 `Display` 渲染图，隐藏 `Code` 源码；不采用图与代码并排模式，正文、callout、折叠区与交付预览同样适用 |

一级章节英文命名中的连接词仅按完整单词匹配：`and`、`AND`、`And` 均写为 `&`。例如 `STRUCTURE AND FUNCTION 结构与功能` 写为 `STRUCTURE & FUNCTION 结构与功能`；其他单词内部字母、中文、编号与样式保持不变。此规则仅适用于学科正文 H1，不扩展到页面或数据库名称、H2–H4、正文、引用、代码或公式；只在新建或获准整理对应章节名时执行。

H2、H3、H4 采用标题式大小写（Title Case）：主要单词（名词、代词、动词、形容词、副词等）首字母大写；冠词、并列连词和介词通常小写，如 `a`、`an`、`the`、`and`、`or`、`but`、`of`、`in`、`on`、`for`、`with`。标题首尾单词首字母大写；`US`、`AI`、`DHL`、`iPhone`、`eCommerce` 等缩写、产品名和专有名词保留规范写法。

简短命名与大小写示例：`Customer Segments 客户群体`、`AI Applications 人工智能应用`；学科架构可参考 `Group Basics 群基础`、`Group Types 群类型`、`Group Structures 群结构`、`Group Morphisms 群态射`、`Group Actions 群作用`。数量与词数是优先范围，不为符合形式删减有效内容，已有术语和明确结构继续保留。

学科导论开头固定为未编号的 H1 `INTRODUCTION 导论`、H2 `A. Overview 概述`、H3 `a. Definition 定义`，其下同组原生罗马数字列表依次为 `i. Definition 定义:`、`ii. Position 定位:`。首个 Definition 正文写 `简称, 全称, 解释`，无通行简称时写 `全称, 解释`，分隔固定为半角逗号加一个空格。导论保留 H1 主题背景色，第一个实质章节从 `I` 开始；详见[固定导论模板](../workflow.md#学科导论固定模板)。公司等其他页面按各自模板处理。标题和加粗标签通常以冒号结尾；历史页面写法不一致时，保留局部习惯。

H2 蓝色文字、H3 橙色文字、H4 黄色文字。H1 使用文本背景色，取本笔记主题色。

**主题色定义**：公司笔记对应品牌色，学科笔记对应本学科主题色。先沿用本笔记已经定义或使用过的主题色；没有时，再从相邻笔记中查找同一公司、同一学科或明确适用于本主题的已有配色。不套用仅在位置上相邻、主题却无关的颜色。具体优先级以主文件“本笔记主题色的定义与选择顺序”为准。

## 五层结构示意

井号后加一个空格。一至四级标题编号依次为 `I → A → a → I`，第五级通过小写罗马数字原生有序列表 `i → ii → iii` 实现。在知识层级上它承担最小知识单位的标题作用，实际不是 H5 块。可以用 Definition 等标签解释上级概念的属性，也可以直接用一个独立术语作标签；标签后软换行解释全称与含义，整个条目仍留在同一列表块内。具体以[第五级语义规则](../workflow.md#第五级的知识单元与解释角度)为准。

独立术语条目示例（不要求额外套一组属性清单）：

```text
<ol type="i">
<li>
<b>CPU 中央处理器:</b><br />CPU, Central Processing Unit 中央处理器, 执行指令并协调计算机运算的核心处理部件
</li>
</ol>
```

```text
# I. TOPIC 主题:
## A. Main Topic 主要主题:
### a. Subtopic 子主题:
#### I. Detailed Topic 细分主题:
<ol type="i">
<li>
<b>Definition 定义:</b><br />解释内容
</li>
<li>
<b>Example 示例:</b><br />示例内容
</li>
</ol>
```

上例中的 `<ol type="i">` 与 `<li>` 是 Notion MCP 正文格式中的原生列表写法；写入前读取当前接口规范。普通 Markdown 的 `1.` 不指定罗马数字样式，手写 `i.` 也不能代替原生列表。若实际工具无法设置，明确报告编号样式未完成。

写入 Notion 时核实四级标题的实际支持情况；无法原样呈现时说明限制，不把降级格式报告为原生 H4。写入后回读核对 `<ol type="i">`、条目内容、数量与嵌套；页面显示需另行核验。

## 数学概念示例

含公式的条目固定为“第一行名称 → 第二行框选行内公式 → 第三行起解释”, 三部分均在同一原生有序列表块内, 使用 `<br>` 保留软换行。

具体规则以主文件[数学概念的解释规范](../workflow.md#数学概念的解释规范)为准。以下示例使用 H4 与原生罗马数字有序列表；实际写入沿用当前知识层级。定义与判定在左侧, 短直觉与例子优先放对应右侧说明区, 不把双栏布局的制作说明写进笔记正文。

#### I. Monomorphism 单态射:

<ol type="i">
<li>
**Definition 定义:**<br>Monomorphism 单态射, 又称 Injective Homomorphism 单射同态, 即同时满足同态性与单射性的映射
</li>
<li>
**Formal Definition 形式化定义:**<br>$\boxed{\forall a,b\in G,\quad\phi(a)=\phi(b)\Rightarrow a=b}$<br>前提是 $\phi:G\to H$ 为群同态, 该式表示不同元素不会映到同一个像
</li>
<li>
**Kernel Criterion 核判定:**<br>$\boxed{\phi\text{ is injective}\iff\ker\phi=\{e_G\}}$<br>前提是 $\phi:G\to H$ 为群同态, 其中 $\ker\phi=\{g\in G:\phi(g)=e_H\}$, $e_G,e_H$ 分别为两个群的单位元；只有单位元映到 $e_H$ 时, 不会合并不同元素
</li>
</ol>

右侧辅助内容示例：

**Intuition 直觉:**<br>
不同元素不会被映射到同一个元素, 因而不会合并原群中的元素

<callout color="gray_bg">
**Examples 例子:**

<ol type="i">
<li>
**Mapping 映射:**<br>$\boxed{\phi:(\mathbb Z,+)\to(\mathbb Z,+),\quad\phi(n)=2n}$<br>这是群同态, 因为 $2(m+n)=2m+2n$
</li>
<li>
**Injectivity 单射性:**<br>$\boxed{2m=2n\Rightarrow m=n}$<br>两个像相同必有原像相同, 因而是单态射；奇数不在像中, 所以不是满射
</li>
</ol>
</callout>

这是群论语境中的用法, 不将“单态射就是单射同态”未经核实地推广至任意范畴。示例只展示所需角度, 不要求追加空的 Motivation、Properties 或 Theorems 条目。

### 精简公式、多条性质与左右例子

下方为一般线性群的版式模板, 使用 H3 概念标题, 下设统一的 H4 `I. Definition 定义` 与 `II. Properties 性质`；第五级统一使用 `<ol type="i">` 原生罗马数字列表。左侧例子使用符号加一个空格及名称, 右侧完整例子包在浅灰色 callout 中。`GL_n(F)` 的集合公式定义一般线性群；更一般的矩阵群是其子群, 可用 `G\leq GL_n(F)` 简记, 不将两者混作同一个概念。

```text
<columns>
	<column ratio="60">
		### a. General Linear Group 一般线性群:
		#### I. Definition 定义:

		<ol type="i">
		<li>
		**Definition 定义:**<br>General Linear Group 一般线性群, 域 F 上所有 n 阶可逆矩阵在矩阵乘法下组成的群
		</li>
		<li>
		**Formal Definition 形式化定义:**<br>$\boxed{GL_n(F)=\{A\in M_n(F):\det A\neq 0\}}$<br>其中 $M_n(F)$ 表示所有 $n\times n$ 的 $F$ 上矩阵
		</li>
		<li>
		**Examples 例子:**<br>$GL_2(\mathbb R)$ 二阶实一般线性群, $GL_3(\mathbb C)$ 三阶复一般线性群
		</li>
		</ol>

		#### II. Properties 性质:

		<ol type="i">
		<li>
		**Identity 单位元:**<br>$\boxed{e=I_n}$<br>单位元是 $n$ 阶单位矩阵
		</li>
		<li>
		**Inverse 逆元:**<br>$\boxed{AA^{-1}=A^{-1}A=I_n}$<br>$A$ 的群逆元就是其逆矩阵
		</li>
		<li>
		**Product Inverse 乘积的逆:**<br>$\boxed{(AB)^{-1}=B^{-1}A^{-1}}$<br>乘积求逆时先后顺序反转
		</li>
		</ol>
	</column>
	<column ratio="40">
		<callout color="gray_bg">
			**Example 例子:**

			<ol type="i">
			<li>
			**Matrix 矩阵:**<br>$\boxed{A=\begin{pmatrix}1&1\\0&1\end{pmatrix}}$<br>这是一个二阶实矩阵
			</li>
			<li>
			**Membership 成员判定:**<br>$\boxed{\det A=1\neq0}$<br>因此 $A\in GL_2(\mathbb R)$
			</li>
			<li>
			**Inverse 逆矩阵:**<br>$\boxed{A^{-1}=\begin{pmatrix}1&-1\\0&1\end{pmatrix}}$<br>直接相乘可得 $AA^{-1}=A^{-1}A=I_2$
			</li>
			</ol>
		</callout>
	</column>
</columns>
```

## 知识树页面

适用于学科、软件概念、工具和编程语言。

学科笔记的左侧正文区围绕概念、定义、公式、推导、性质和方法组织。学习路线、学习顺序与学习建议默认不添加；确有帮助且已有合适的右侧说明区时，可在那里简短呈现。不要把学习路线设成左侧正文区的章节，也不要仅为它创建双栏。学习问题、例子、计算和图示可按需放在右侧；页面没有第二个实质信息面板时保持单栏。

导论的 `Core Questions 核心问题` 按需作为第五级内容，接在 Position 后，使用同组原生罗马数字列表中的 `iii. Core Questions 核心问题:`；条目写作 `<li>**Core Questions 核心问题:**<br>本学科试图回答的主要问题</li>`，不默认另设 H2，也不创建 H5。下方固定模板只列必需的 Definition、Position，核心问题有实质内容时再追加。

起源或历史仅在一级学科确有需要时考虑，末端学科专题笔记不默认设置；已有有效内容继续保留，不为统一模板自动删除历史笔记内容。

### 学科父页模板

包含分支学科数据库的学科父页，正文开头按以下顺序排列：

1. 第一行是未编号的一级标题 `INTRODUCTION 导论`，使用该页主题背景色。
2. 下一块紧接现有分支学科数据库，保留它的数据库身份、父子关系、视图和数据。
3. 数据库之后放固定导论双栏：左栏从 `A. Overview 概述` 开始，包含 `a. Definition 定义` 及原生罗马数字列表中的 Definition、Position 两项；右栏顶部放本学科当前封面，与 Overview 并列。后续 `B、C` 等二级标题及各节正文按内容需要确定。

```text
# INTRODUCTION 导论: {color="本页主题色_bg"}
[现有分支学科数据库块，原样保留]
<columns>
	<column ratio="60">
		## A. Overview 概述: {color="blue"}
		### a. Definition 定义: {color="orange"}
		<ol type="i">
		<li>**Definition 定义:**<br>简称, 全称, 解释</li>
		<li>**Position 定位:**<br>按需要简述上级归属、相邻学科的边界及在知识体系中的作用</li>
		</ol>
	</column>
	<column ratio="40">
		[本学科当前封面图片块，使用已读取的封面资源]
	</column>
</columns>
```

模板中的封面图片块也只是位置示意，实际使用本学科当前封面的真实资源；Overview 与封面固定在同一组双栏，保留封面版本和页面封面属性。示例的 60/40 仅用于新建默认值，已有比例不照抄覆盖。

方括号一行仅表示块的位置，不是可写入 Notion 的正文；实际操作须使用读取到的原生数据库块，不能用文字或链接代替。不要在 INTRODUCTION 与数据库之间插入概述、定义、二级标题或其他说明，也不要仅为套用模板新建数据库。

重排后核对前三部分的顺序，并确认分支数据库和原有内容均保留。这项模板用于学科父页；公司研究和行业 Wiki 仍使用各自的专用架构。

### 学科联系折叠列表

`Connections 学科联系` 放在相关正文的右侧说明区，使用原生 Toggle List，不作为左侧正文或双栏外的编号章节，也不用 Toggle Heading。折叠标签使用加粗双语名称，展开后列出相关学科、联系说明与原生页面引用，保留有效内容与已有链接。仅在当前授权范围内调整历史内容；本规则不授权批量迁移其他页面。

Notion enhanced Markdown 以 `<details>` 表达 Toggle List；将下列结构嵌入右侧 `<column>`，按实际目标页面补充原生 `<mention-page>` 引用：

```text
<details>
<summary>**Connections 学科联系:**</summary>
	1. **Related Discipline 相关学科:**<br>说明与当前主题的联系，附对应学科的原生页面引用
</details>
```

### 双栏范围与长度平衡

- 全部 H1（包括 `INTRODUCTION`）独立整行，始终放在双栏外；H2、H3、H4 与第五层有序列表按两侧实际长度选择放在左栏或双栏外。第五层不改为标题块。
- 新建双栏默认左 60% / 右 40%，可视内容采用 5:5、6:4 或 7:3；已有双栏比例与用户手动调整保持不动，尤其不把非 5:5 当成错误，不为套用默认值或对齐而改宽度。用户明确要求调整已有比例时才修改。导论固定 Overview 左、当前学科封面右，H1 在双栏外；右侧例子用加粗双语标签，不作为正文编号章节。
- 导论双栏固定从 H2 `A. Overview` 开始，右栏展示当前学科封面。其他正文可从 H2、H3、H4 或完整列表段落开始双栏，也可在较低层级边界拆分或合并；不强制每个二级小节各自成对，不拆开 Overview 与封面的固定并列关系。
- 优先保持知识单元完整和图文对应；同一一级章节内，右侧插图或例子可在不影响对应关系时与邻近相关正文适度错位，不要求逐段严格对齐。标签须足够清楚，不为长度平衡打乱用户已调整的布局，不把无关或跨章内容拿来凑齐。
- 两侧底部相差约 5 行显示文本的高度只作视觉参考，超过不自动触发重排、拆栏或合栏；按实际栏宽下的渲染估算，不按源文件换行数。图、表、公式与 callout 也按视觉高度计入；无法查看渲染时只报告长度估算，不声称精确对齐。
- 保留用户已调整的布局，包括既有分组、比例和图文位置。只有明显影响阅读且本次允许调整排版时，才在完整内容边界调整双栏，优先保持知识单元完整和图文对应；比例调整仍遵守保留已有比例的规则。不刻意补空白，不为等高删减内容、扩写无关文字或添加占位图。
- 短例子、手算和易错提醒可用浅灰色 `gray_bg` callout；较宽表格和插图可直接放右侧，不要求统一包装。

### 流程图显示与检查

- 默认所有 flowchart 及 Mermaid 状态图、时序图等只显示 `Display` 渲染图。图形源码仅用于制作，不另放入正文、右栏、callout、折叠区、代码附件或交付回复；用户明确索取图源码时遵从该次要求。
- 原生图块优先设置为 `Display`，不显示 `Code` 或图与源码并排视图。写入 Mermaid Markdown 不代表显示模式已设置，不能臆造接口属性；有编辑器 UI 时可切换并检查实际图形。界面显示 `Preview` 或 “Show only preview and hide code” 时，按仅显示图形、隐藏源码的实际行为识别 Display 模式。
- 当前工具无法控制显示模式时，可嵌入已渲染的图像；核对节点、箭头和标签，保留原有有效资源及必要的可编辑来源。不能以隐藏源码为由删除图，也不把未经实际查看的显示状态报告为已验证。
- 检查正文、双栏、callout、折叠与嵌套块，以及预览、最终回复和附件中是否露出图源码或重复图。整页替换、复制或重建图块后重新核对显示模式，切换后在实际界面确认图形保留且源码隐藏。此规则不禁止用于解释程序本身的 HDL、Python 等代码示例，也不授权批量更改历史页面。

下面仅演示 H1 与双栏的嵌套关系，实际正文沿用页面既有标题与内容；此处是维护模板的结构源码，不是交付给用户的流程图：

```text
# I. TOPIC 主题: {color="gray_bg"}
<columns>
	<column ratio="60">
		## A. Main Topic 主要主题: {color="blue"}
		### a. Concept 概念: {color="orange"}
		1. **Definition 定义:**<br>正文定义与机制
	</column>
	<column ratio="40">
		<callout color="gray_bg">
			**Example 例子:**<br>辅助解释与手算
		</callout>
	</column>
</columns>
```

### 专题正文页

以下保留原有章节示例，并同步固定导论开头。新写内容的大小写、配色和列表标签仍按上方规则执行；例如新 H1 使用全大写英文，新列表项加粗标签并在块内换行。

```text
# INTRODUCTION 导论:
<columns>
	<column ratio="60">
		## A. Overview 概述:
		### a. Definition 定义:
		<ol type="i">
		<li>**Definition 定义:**<br>简称, 全称, 解释</li>
		<li>**Position 定位:**<br>按需要简述上级归属、相邻学科的边界及在知识体系中的作用</li>
		</ol>
	</column>
	<column ratio="40">
		[本学科当前封面图片块，使用已读取的封面资源]
	</column>
</columns>

# I. FIRST DOMAIN 第一部分:
## A. Subtopic 子主题:
### a. Concept 概念:
1. **Term 术语:**
```

没有分支学科数据库的专题正文页使用上述固定导论开头，其余章节沿用实际结构，不需要套用父页的数据库位置模板或新建数据库。

参考页面（ID 保持原样）：

- Git 吉特：`30eab59a-584f-80cf-a2e6-c08bb7bd28a0`
- JAVA 爪哇：`1faab59a-584f-806c-b89b-d936d9b34711`
- SOFTWARE ENGINEERING 软件工程：`1faab59a-584f-8072-8c61-c96f862c3212`

## 公司研究页面

专用规则使用 [公司笔记管家](../../../../industry-notes/references/notion-company-steward/workflow.md)，以下保留旧链接入口。

### 数据库字段

见 [企业字段规范](../../../../industry-notes/references/notion-company-steward/references/company-database-fields.md) 与 [历史字段复用](../../../../industry-notes/references/notion-company-steward/references/company-guide.md#数据库字段)。

### 公司品牌配色

见 [公司品牌配色](../../../../industry-notes/references/notion-company-steward/references/company-guide.md#公司品牌配色)。

### 公司研究模板

见 [详细公司研究模板](../../../../industry-notes/references/notion-company-steward/references/company-guide.md#公司研究模板)。简短概览任务遵循公司 skill 主文件，不强制填满详细模板。

## 个人项目页面

适用于业务、转型计划和持续推进的个人项目。保留通用层级，同时允许执行事项、内嵌数据库、进度记录和按时间更新的内容。现有页面支持时，将稳定的项目介绍与持续变化的计划分开。

参考页面：

- HARVESTFLOW 德馨淼盛：`222ab59a-584f-802e-b890-fb2a58f47cf8`

## 日记页面

日记允许更灵活的结构。保留按时间、季度、课程或地点组织的方式，不强套知识树的简介模板。只有编号有助于导航时，才使用带编号的 H1。

参考页面：

- Journal of Davis 戴维斯日记：`312ab59a-584f-8016-9d3a-f866146518ef`

## 历史差异：不要静默统一

- `DAIRY 日记` 可能是有意命名或历史标签，即使通常拼作 `DIARY`，也不要擅自改动。
- 用户未要求重命名页面或分支时，可保留历史大小写。新增标题或受托统一标题时，执行英文大写、简称优先、双语命名规则。
- `Introduction 简介`、`Introduction 导论`、大小写、加粗和末尾冒号存在差异。
- 部分页面重复小节字母，或混用纯中文与双语标题。
- 不同行业分支的公司数据库结构存在差异。

用户要求统一时，先列出限定范围的修改清单，区分错字修正、视觉格式统一、数据库结构变更与页面移动。
