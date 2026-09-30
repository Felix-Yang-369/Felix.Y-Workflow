# 参数化提示词模板

A–C 仅适用于选定的工程图解海报系列。已有认可系列时使用 D；用户要求非电影感、右侧标题或更少元素时，不拼接 A–C 中冲突的默认语句。

填入 `TITLE`、`HERO`、`DIAGRAMS`、`ACCENT`、`MICROCOPY` 和 `USE`。图像模型能否可靠生成文字取决于具体工具；默认使用**无字底图提示词＋精确文字叠加说明**。用户明确希望一次生成带字海报时，使用第二版并校对文字。

## A. 无字底图，供精确排字

```text
Create a premium 16:9 cinematic editorial cover for [TOPIC], in the visual language of a high-end engineering atlas. Deep near-black and graphite background, subtle technical grid, controlled atmosphere, physically plausible materials, crisp details and strong depth. One dominant [HERO] occupies the right 55–60% of the frame, lit with restrained [ACCENT] rim light. Reserve a clean, dark, high-contrast title area in the left 40–45%, with the title block intended to sit slightly above the image's vertical midpoint, never against the top edge. In the lower-left area, arrange three to five small modular technical diagrams showing [DIAGRAMS], with fine [ACCENT] linework, precise panel borders and generous spacing. Add only topic-relevant schematics around the hero; each diagram should explain a different aspect of the subject. Cohesive [ACCENT] color echoes through the schematic lines and edge lights, while the main materials remain realistic and mostly neutral. Dense enough to feel expert, clear enough to read as a thumbnail. No rendered words, letters, numbers, equations, logos, watermarks, random UI, unrelated machinery, excessive neon or illegible microtext.
```

后期文字规格：在左侧中上区域放 `TITLE`，标题块的视觉中心略高于画面水平中线，顶部留出明显呼吸空间；英文全大写，最多两行。第一行金属白或暖白，第二行使用 `ACCENT` 的低饱和亮色。`MICROCOPY` 若提供，放在标题下方一行，用较小但仍清楚的字重。不要把参考图的小字、假参数或公式原样搬入新图。

## B. 一次生成带字海报

```text
Create a premium 16:9 cinematic editorial engineering-atlas poster for [TOPIC]. Use a deep near-black and graphite background with a subtle technical grid. In the left 40–45%, set the exact title “[TITLE]” in very large, bold, readable uppercase English, on no more than two lines. Place the title block slightly above the image's vertical midpoint, with generous empty space above it; do not place it against the top edge. Spell every letter exactly and add no other headline. Use metallic white for the first line and a restrained [ACCENT] tint for the second. If provided, place only this short subline below the title: “[MICROCOPY]”. On the right 55–60%, show one large, physically credible [HERO] with dramatic but controlled [ACCENT] rim lighting. Along the lower left, place three to five neatly separated schematic panels showing [DIAGRAMS]. Technical linework and panel rules share the [ACCENT] color; diagrams must be relevant to the topic and visually distinct. Keep the hero and title dominant at thumbnail size. No extra words, gibberish labels, fake measurements, logos, watermarks, unrelated machines or overbright neon effects.
```

若生成结果出现错字、伪公式或虚构设备参数，换用 A 版或修正后再交付。不能把提示词中的 “exact” 当作成品已准确的证据。

## C. Notion 横幅适配

在 A 或 B 版末尾加入：

```text
This will also be cropped into a shallow Notion cover and gallery card. Keep any required title on the left, slightly above the image's vertical midpoint, and check that it remains visible in the wide horizontal crop. Keep the essential hero silhouette within the central safe region. Extend only decorative grid, lighting and nonessential schematic fragments to the edges.
```

若文字不是用户明确要求，选 A 版并移除“后期文字规格”。如主题较抽象，`HERO` 可改为一个有物理质感的模型、标本或场景；不要强加电路板、芯片、发动机或起重机。

## D. 已认可系列与局部修改

```text
Use the provided approved image as the editing reference for [TOPIC].
Requested change only: [DELTA].
Preserve: [approved title text and placement unless targeted, composition, subject identity, element count, background, natural material colors, lighting, aspect ratio].
Series settings: [approved style and crop-safe layout].
Apply the requested change without introducing a new composition, cinematic treatment, decorative labels, or unrelated elements.
```

`DELTA` 写具体变更，如“仅把绿色强调色换成紫色，保留主体自然颜色”。先看参考图再编辑，完成后与参考对照；上述保留要求不是已经验证的结果。若同系列新图而非修改旧图，沿用固定项，仅替换已确定的单张变量。
