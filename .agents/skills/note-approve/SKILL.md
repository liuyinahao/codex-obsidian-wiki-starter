---
name: note-approve
description: 在用户明确接受已扩写并返修的课堂或方法笔记后，创建可追溯副本并送入 Raw ingest 队列。
---

# note-approve

仅在用户明确接受某份已扩写、且已检查或返修的 `notes/class/` 或 `notes/method/` 笔记时使用。

1. 读取 `AGENTS.md`、指定笔记、`raw/index.md` 与 `wiki/log.md`；确认用户是在接受扩写而不是继续修改。
2. 保留原笔记和文件夹结构不动。以当前版本创建单篇 Raw 批次：`raw/unprocessed/note-approve/YYYY-MM-DD-HHmm-原笔记名/原笔记名.md`。目标已存在时停止报告，不得覆盖或自动改名。
3. 副本保留原正文与 frontmatter；只添加/更新 `processing_status: unprocessed`、`origin_note` 和 `note_approved_at`。没有 frontmatter 时在副本前新增。不得重新扩写或改排副本正文。
4. 在 `raw/index.md` 登记未处理副本及 `origin_note`，在 `wiki/log.md` 追加 `note-approve` 日志；此时不创建来源页或主题页。
5. 停止等待后续 ingest 请求。来源页必须回链原笔记，原笔记始终不改动。
