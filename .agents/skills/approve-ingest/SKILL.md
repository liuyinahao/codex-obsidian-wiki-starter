---
name: approve-ingest
description: 在用户明确批准后，归档 pending_review 的原始资料及关联附件，并修复本地 Raw 引用。
---

# approve-ingest

仅在用户明确批准某个 `pending_review` ingest 单元后使用。

1. 读取 `AGENTS.md`、`raw/index.md`、`wiki/log.md`，定位被批准的 Markdown 或批次。
2. 找到同名、`attachments` 或 `ingest_group` 关联的附件；必须与 Markdown 整组归档。
3. 核对来源页、`processed_into` 与索引记录；不一致时停止报告。
4. 仅更新 Markdown 的 `processing_status: processed`、`reviewed_at` 与 `processed_at`；不改 PDF/附件。
5. 迁移前检查 `raw/processed/` 的目标路径冲突。无冲突时迁移根目录文件或整个批次目录；有冲突时停止，不得覆盖或自动改名。
6. 修复指向旧 `raw/unprocessed/` 路径的来源页/正文链接，更新两个索引和日志，并报告残留路径自检结果。

不得大幅改写 Wiki 正文或重组用户目录。
