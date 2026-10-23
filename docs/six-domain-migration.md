# 六类入口迁移 · 0.5.0

版本 0.4.21 → 0.5.0：一个 FELIX WORKFLOW 插件总包，六个可调用的领域 Skill。原 13 项工作流全文及全部参考、素材和 UI 元数据保存在各领域的 `references/<original-workflow>/`，原 `SKILL.md` 正文改名为 `workflow.md`。金融管理的 `cashflow.md` 和 `portfolio.md` 是新增方法文件。

- [六个入口与全部独立文件](workflows.md)
- [旧名到新位置的完整索引](../plugins/felix-workflows/references/skill-map.md)
- [65 个原文件的路径与 SHA-256 清单](../plugins/felix-workflows/references/migration-map.json)
- [最新数据库规则与未决差异](../plugins/felix-workflows/references/migration-notes.md)
- [发布前文档完整原文](preserved/README.md)
- [源码编辑与重新安装](customization.md)

本轮沿用磁盘最新保存内容，不从旧缓存恢复文本，不摘要压缩原模块。迁移只调整必要的相对链接和一个已失效标题片段；这次 GitHub 发布保持包内 92 个文件逐字节不变。旧名是文件导航标识，不是额外的宿主调用别名。

你刚修改的数据库视图、学科主题色、学科难度、学科分支、学习进度及页面布局规则全部保留，包括原文尚未统一之处。发布本身不作业务页面、日历、金融账户或学习进度写入。

静态结构、内容保留、文档链接和源码／安装文件一致性分别检查；真实新会话调用和业务页面视觉显示仍需按实际任务验收。
