# 参数化提示词模板

填入 `TITLE`、`HERO`、`DIAGRAMS`、`ACCENT`、`MICROCOPY` 和 `USE`。默认遵循 Felix 已确认的效果：平面标题、无标题装饰横线、适度写实背景与学科图解。场景与材质按主题选择，不统一套用玻璃桌面。默认使用无字底图＋精确文字叠加；一次生成带字海报时使用 B 并校对文字。

## A. 无字底图，供精确排字

```text
Create a premium 16:9 cinematic editorial academic cover for [TOPIC]. Use a restrained background with a modest photographic quality: topic-appropriate tangible materials, believable reflections, soft contact shadows, natural directional light and subtle depth of field. Keep the subject a clear conceptual educational visualization. One dominant [HERO] occupies the right 55–60% of the frame with controlled [ACCENT] lighting. Reserve a clean title area in the left 40–45%, slightly above the image's vertical midpoint, with breathing space above. Do not bracket this area with decorative horizontal rules, diamonds or ornaments. Along the lower left, arrange three to five complementary diagrams showing [DIAGRAMS], with restrained linework and generous spacing. Meaningful diagram borders, axes and arrows are allowed. Use a cohesive [ACCENT] with neutral background materials. Keep the hero recognizable at thumbnail size. No rendered words, letters, numbers, equations, logos, watermarks, unrelated machinery, excessive neon, floating particles, decorative network clutter or microtext.
```

后期文字规格：左侧中上区域放 `TITLE`，视觉中心略高于水平中线，顶部留出呼吸空间；英文全大写，最多两行。使用清晰、有分量的平面字体，可用衬线字体；第一行白或暖白，第二行可用浅主题色。不要铜色或金属字、立体挤出、浮雕、倒角、厚重投影，也不要标题上下的装饰横线、菱形或花纹。`MICROCOPY` 仅在提供时加入。不要复制参考图的小字、假参数或公式。

## B. 一次生成带字海报

```text
Create a premium 16:9 cinematic editorial academic cover for [TOPIC]. In the left 40–45%, set the exact title “[TITLE]” in large clear FLAT two-dimensional uppercase typography on no more than two lines. Use a substantial elegant editorial typeface, matte white or warm white for the first line and optionally pale [ACCENT] for the second. Position the title slightly above the vertical midpoint with breathing space above. Spell every letter exactly. No metallic or copper lettering, embossing, extrusion, bevels or dimensional letter shadows. No decorative horizontal lines, diamonds or flourishes above or below the title. If provided, include only this subline: “[MICROCOPY]”. On the right 55–60%, show one dominant [HERO], grounded in a subtly photographic setting with topic-appropriate real materials, believable reflections, soft contact shadows, natural directional light and subtle depth of field. Preserve conceptual mathematical or scientific visualization with convincing material presence. Do not add unrelated equipment or force every subject into the same laboratory or tabletop scene. Along the lower left, place three to five clean complementary diagrams showing [DIAGRAMS]. Use restrained [ACCENT] linework; meaningful panel borders, axes and arrows are allowed. Keep title and hero dominant at thumbnail size. No extra words, fake equations, gibberish labels, invented measurements, logos, watermarks, excessive neon or particle clutter.
```

若出现错字、伪公式或虚构参数，换用 A 或修正后再交付。不能把提示词中的 “exact” 当作成品已准确的证据。检查标题确实为平面字，且上下没有残留横线或菱形。

## C. Notion 横幅适配

在 A 或 B 末尾加入：

```text
This will also be cropped into a shallow Notion cover and gallery card. Keep the required title on the left, slightly above the vertical midpoint, and check that it remains visible in the wide horizontal crop. Keep the essential hero silhouette within the central safe region. Extend only nonessential background texture, lighting and schematic fragments to the edges.
```

若文字不是用户明确要求，选 A 并移除后期文字规格。抽象主题可使用有真实材质与光影的数学模型或概念展示；不要强加电路板、芯片、发动机或起重机。

## D. 已确认参考与局部修改

- 参考 [Harmonic Analysis](../assets/harmonic-analysis-approved.png) 的平面白／浅蓝标题、无横线排版、可信玻璃材质和自然光影；其他学科替换主体与辅助图解。
- 用户认可画面后，只要求去除标题横线或调整字体时，使用成品做局部编辑，锁定背景、主体、图解与构图，不重新设计整张封面。
- 删除标题装饰横线时保留图解坐标轴、面板边框与必要箭头。
