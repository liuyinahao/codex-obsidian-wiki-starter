# 给 Codex 的说明

这个文件供维护者理解启动包，不代替根目录 `AGENTS.md`。执行任何工作前先读取 `AGENTS.md`，再按请求选择项目级 skill。

## Skills 选择表

| 用户请求 | 读取的 skill |
|---|---|
| 整理 `notes/class` 或 `notes/method` 笔记 | `expand-notes` |
| 用户明确接受笔记扩写 | `note-approve` |
| 处理 Raw 网页、PDF 或批次 | `ingest-raw` |
| 用户批准待审阅资料归档 | `approve-ingest` |
| 基于 Wiki 回答问题 | `query-wiki` |
| 将高价值回答沉淀回 Wiki | `inspool` |
| 检查链接、证据链、索引和队列 | `lint-wiki` |

## 必须维护的同步点

| 操作 | 必须同步 |
|---|---|
| `expand-notes` | 原笔记；必要时 Wiki、索引与日志 |
| `note-approve` | Raw 副本、`raw/index.md`、`wiki/log.md` |
| `ingest-raw` | 来源页、主题页、两个索引、日志、Raw frontmatter |
| `approve-ingest` | Raw 路径、来源页 Raw 链接、两个索引、日志 |
| `inspool` | 目标 Wiki 页、`wiki/index.md`、`wiki/log.md` |
| `lint-wiki` | 问题清单、低风险修复、`wiki/log.md` |

## 权限与质量边界

- Raw 正文不改写；附件不写 frontmatter。
- `pending_review` 不移动，除非用户明确批准。
- 用户创建的笔记标题和分类结构不重组。
- 资料冲突、证据不足、外链访问失败必须显式保留。
- 普通 Clip 不展开链接；重点 Clip 才扩大阅读范围。
- 处理个人、患者、未公开研究或基因组数据前，先确认可使用本地脱敏版本。

## 交付格式

每次 ingest 先说明选定单元、资料判断与预期写入；结束时列出更新页面、Raw 状态和需要用户审阅的点。不要把复杂任务伪装成只生成一个孤立摘要页。
