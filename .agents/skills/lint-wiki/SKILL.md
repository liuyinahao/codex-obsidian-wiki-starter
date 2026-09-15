---
name: lint-wiki
description: 检查 Wiki 的证据链、链接、索引与 Raw 队列/批次状态，并只修复低风险问题。
---

# lint-wiki

读取 `AGENTS.md`、`wiki/index.md`、`raw/index.md`、`wiki/log.md`，递归检查 `wiki/sources/` 与三个主题目录。

检查：孤立页、缺少来源支撑的强结论、未标注推断、失效链接、重复页、索引/流程状态不一致、关联 Markdown/PDF 未成组、批准后遗留旧 Raw 路径、长时间待审阅和过大批次。

- Safari 新 Clip 位于 `raw/unprocessed/` 根目录是正常状态；为 ingest 创建子文件夹批次也是正常状态。
- 用户建立的主题分类目录必须递归兼容，不能移动、删除或重组。
- 先输出按优先级排序的问题清单；只修复低风险链接或索引问题。
- 涉及内容判断、原始资料迁移、目录结构或大规模重命名时，先报告并等待用户决定。
- 将 lint 结果写入 `wiki/log.md`。
