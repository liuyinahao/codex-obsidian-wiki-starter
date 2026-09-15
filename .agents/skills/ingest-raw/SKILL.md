---
name: ingest-raw
description: 处理 raw/unprocessed 中的一条网页资料或一个批次及其关联附件，沉淀为来源页与知识 Wiki，并停在待审阅。
---

# ingest-raw

先读取根目录 `AGENTS.md`，再处理用户指定资料，或 `raw/unprocessed/` 中下一条 Markdown 原始资料。

1. 读取 `raw/index.md`、`wiki/index.md`、`wiki/log.md` 并扫描 `raw/unprocessed/`。
2. 按 `AGENTS.md` 选择 ingest 单元：子文件夹批次、关联附件、共同 `ingest_group`、用户指定组合或单篇 Markdown。
3. 先说明选中资料、内容判断与预计更新页面；无法判断归入文献综合、实验方法还是研究方向时，停下询问。
4. Raw Markdown 正文保持不变。按标题末尾 `*` 判定重点 Clip：
   - **重点 Clip**：清点并阅读关联的本地/必要外链图片、PDF、数据、视频和补充材料；图片必须实际查看；本地副本优先。参考文献链接不展开。无法读取的应读材料写入来源页待确认问题。
   - **普通 Clip**：只读本地 Markdown 与 frontmatter，不展开正文链接或附件，除非用户另行要求。
5. 在 `wiki/sources/` 创建或更新证据页，记录 Raw 链接、外部信息和实际证据范围。含 `origin_note` 时，必须回链原笔记但不得改原笔记。
6. 按内容创建/更新知识页：结论与比较 → `wiki/literature-synthesis/`；操作与排错 → `wiki/experimental-methods/`；假设与研究问题 → `wiki/research-directions/`。区分来源事实、综合判断和待验证推断。
7. 更新 `wiki/index.md`、`raw/index.md` 和 `wiki/log.md` 后，才把关联 Markdown 标为 `processing_status: pending_review`。附件不写 frontmatter。
8. 停在待审阅；不得自动迁入 `raw/processed/`。
