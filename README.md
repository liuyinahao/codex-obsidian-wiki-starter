# Codex + Obsidian Wiki 启动包

这是一个可从零开始使用的本地知识库工作流：Safari Web Clipper 负责收集，Codex 负责整理与维护，Obsidian 负责浏览、链接和长期保存。

它不包含任何示例中的私人笔记、网页剪藏或研究内容；复制整个文件夹后即可作为新的 Obsidian Vault，也可直接作为 Codex 项目打开。

## 你会得到什么

- 一条可审阅的资料流：`raw/unprocessed → pending_review → processed`。
- 三类可积累的知识页：文献综合、实验方法、研究方向。
- 保留用户原有标题大纲的笔记扩写流程。
- 可选的“笔记接受后送入 ingest”联动流程。
- 供 Codex 自动选择的七个项目级 skills。

## 从零开始：只做这六步

1. 将整个 `Codex-Obsidian-Wiki-Starter` 文件夹复制到你希望存放知识库的位置，并可按喜好重命名。
2. 在 Obsidian 中选择“打开文件夹作为 Vault”。
3. 在 Codex 桌面端把该文件夹作为项目打开；Codex 会先读取根目录 `AGENTS.md`。
4. 阅读 [首次运行](docs/03-首次运行.md)，完成你的个性化选择。
5. 在 Safari 的 Obsidian Web Clipper 中把默认保存路径设为 `raw/unprocessed/`。
6. 剪藏一篇网页后，对 Codex 说“ingest 下一条资料”。它完成后会停在 `pending_review`；你检查后再说“可以归档到 processed”。

## 文档导航

- [工作流总览](docs/01-工作流总览.md)：每一步为什么存在。
- [架构与数据流](docs/02-架构与数据流.md)：文件夹、状态机和证据图谱。
- [首次运行](docs/03-首次运行.md)：新用户的逐步上手清单。
- [操作手册](docs/04-操作手册.md)：日常可直接对 Codex 说什么。
- [个性化设置](docs/05-个性化设置.md)：如何把工作方式改成自己的。
- [给 Codex 的说明](docs/06-给Codex的说明.md)：规则、skills 和维护边界。

## 先记住三条边界

1. `raw/` 是原始事实层。除流程 frontmatter 和批准后的迁移外，Codex 不改写其中正文。
2. ingest 完成不等于归档完成。只有你明确批准后，资料才会进入 `raw/processed/`。
3. 你已有的笔记标题是不可变大纲。Codex 只能在其下扩写，不能重排或改名。

## 可选：在 Obsidian 侧边栏使用 Codex Panel

你也可安装 Codex Panel，将同一工作流放进 Obsidian 右侧边栏。它以本 Vault 根目录作为工作目录，不会自动把当前笔记发送给 Codex。安装方法与范围说明见 [首次运行](docs/03-首次运行.md)。这不是运行本启动包的必要条件。
