# 行业 Wiki 架构观察

此记录基于 2026-09-25 对 Notion「INDUSTRY 行业」的读取和抽样。它用于辨别当前架构；页面、属性及企业归属可能继续变化，编辑前须重新读取目标。

## 根与一级板块

`INDUSTRY 行业` 是 Wiki 根。其下七个一级板块目前是画廊数据库，卡片通常使用页面封面。各库行数：科技 4、消费 5、工业 5、金融 4、医疗 3、地产 3、公共 6。行数是本次读取到的当前视图结果，不是内容总量承诺。

多数一级板块只以标题和少量分类字段承接行业页面，不能假定所有板块字段一致。例如金融板块有 `约占GDP`，医疗板块有 `行业规模`。这类数值或文字属性若无统计时点、范围与来源，不能当作现势事实直接复用。

## 从板块到公司的几条实际路径

| 一级板块数据库 | 二级行业页面 | 三级行业页面及其分类容器 | 末端企业库（有时兼作四级细分标签） | 企业条目 |
|---|---|---|---|---|
| [TECHNOLOGY 科技](https://app.notion.com/p/1f8ab59a584f801680ebd7994943b9c7) | [SOFTWARE 软件](https://app.notion.com/p/1f8ab59a584f80e78e47de2bd1f211c3) | `Branches of Software` 中的 [SOCIAL 社交类](https://app.notion.com/p/1fcab59a584f80db9d26c4b81b772934) | `Social Media 社交类软件` 企业库 | Meta、Tencent 等公司页 |
| [CONSUMER 消费](https://app.notion.com/p/20eab59a584f80f19e2bd5b8b8198b92) | [DURABLES 耐用品](https://app.notion.com/p/30eab59a584f80f181affb1e5304ed58) | `Consumer Durables` 中的 [HOUSEHOLD 家居](https://app.notion.com/p/256ab59a584f8060b065ee32630bb1d3) | `Furniture Giants 家具行业`、`Appliance Giants 家电巨头` 企业库 | Serta、Haier 等公司页 |
| [CONSUMER 消费](https://app.notion.com/p/20eab59a584f80f19e2bd5b8b8198b92) | [CONSUMER SERVICES 消费者服务](https://app.notion.com/p/30eab59a584f8074a1d9e234b0f5703e) | `Consumer Services` 中的 [RESTAURANT 餐饮](https://app.notion.com/p/20aab59a584f80f3bdc1ebadd30e0e87) | `Fast Food Giants`、`Beverage Shops`、`Baking` 企业库 | McDonald's 等公司页 |
| [FINANCIALS 金融](https://app.notion.com/p/21cab59a584f80119709f723188ee6f4) | [BANK 银行](https://app.notion.com/p/263ab59a584f8052b4c6f760d8b85640) | 无单独分类库 | `BANKS GIANTS 银行巨头` 企业库 | JPM 等公司页 |
| [TECHNOLOGY 科技](https://app.notion.com/p/1f8ab59a584f801680ebd7994943b9c7) | [TELECOM 通信](https://app.notion.com/p/20aab59a584f804f8f38c485f85f6cbe) | 无单独分类库 | `Telecom Operator Giants`、`Network Equipment Giants` 企业库 | China Mobile 等公司页 |

这里的“级”指行业语义，不等于 Notion 侧边栏的点击层数。分类数据库只是容器；企业数据库的名称可能承担一个细分行业标签，但其中的行是企业。四级并非每个分支都必须出现。

## 数据库职责与例外

- **分类数据库**：行是行业或细分行业页面。如 `Branches of Software` 的 `SOCIAL`、`AI`，`Branches of Entertainment` 的游戏、影视、音乐等。分类行可以有正文和更深一层企业库。
- **企业数据库**：行是公司或机构页面，标题字段没有统一名称。如芯片库用 `芯片巨头`、社交库用 `公司`、运营商库用 `运营商`、快餐库用 `快餐巨头`、律所库用 `律所`。
- **按角色拆分**：芯片企业库以 `行业角色` 多选属性表示设计、代工、设备、封测等；通信页以两个独立企业库区分运营商与网络设备商。不能把一个板块的拆法复制到所有板块。
- **直接接企业库**：银行、制药、医疗服务等二级行业页面直接嵌入企业库，没有独立的三级分类。它们的正文仍可有 H1/H2/H3 分析层级，标题层级不等于行业分类层级。
- **混合用途**：软件页同时包含细分行业库、`E-COMMERCE 电商` 企业库和跨公司产品对照表；电商库现有外卖、打车、酒旅企业。整理时先说明其平台业务口径，不自动迁移到消费服务板块。
- **早期或稀疏页面**：某些分类页目前以子库或少量正文为主，另一些保留旧式列表、空标题或未注明日期的规模数字。先标记待核实，再按用户授权逐页补全；不因空白或格式差异删除页面。
