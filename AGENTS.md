# Codex + Obsidian Wiki 维护规则

本文件是这个 Vault 的唯一规则入口。Codex 开始工作前必须先阅读它，并把知识库维护视为长期工作，而不是只完成一次聊天回答。

## 目标与默认语言

- 将零散原始资料沉淀为结构化、可交叉引用、可持续演化的 Wiki。
- 默认用中文回复、写 Wiki、写日志和写说明；Raw 原文保留其原语言。
- 关键事实、数字和判断尽量链接到本地 `wiki/sources/` 证据页；事实、综合判断与推测必须区分。

## 目录与所有权

```text
notes/
  class/                  # 用户课堂/会议笔记
  method/                 # 用户方法与实验笔记
raw/
  unprocessed/            # Safari Web Clipper 的默认入口
  processed/              # 经用户批准后的原始资料
  assets/                 # 无法与条目同放的静态资源
wiki/
  sources/                # 证据节点
  literature-synthesis/   # 文献综合、比较、限制
  experimental-methods/   # 方法、参数、排错
  research-directions/    # 灵感、假设、验证问题
  meta/                   # 流程、历史记录
```

- `raw/` 是事实来源层，正文默认只读。只允许改动少量流程 frontmatter；仅在用户批准后可迁移路径。
- `wiki/` 是可维护的知识层，可创建、更新、重命名和交叉链接。
- `notes/` 是用户笔记层。不得擅自创建、删除、重命名或重组其文件夹。
- 用户可在三个主题 Wiki 目录下任意新建或移动分类子文件夹；视为合法组织方式，读取与 lint 必须递归兼容，不能依赖深层路径推断语义。

## 个人偏好：可由用户直接编辑

以下是启动包的默认偏好。用户可以改写这一节；发生冲突时，本节优先于下面的通用规则。

- 笔记标题：所有既有 Markdown 标题的文字、层级和顺序均不可修改。扩写只在原标题下进行；必要时可新增下一级标题；与既有标题同级的补充只能追加至整篇原大纲后。
- 速记改写：关键词和碎句可直接改写为完整可读正文，不保留“原始速记”副本。
- 不确定内容：已确认的信息正常整合；仅当局部内容不能可靠确认且删除会损失价值时，写作 `==修改内容==（待确认：原因）`，不要单列待验证区。
- 冒号补全：若中文冒号 `：` 后只有空格或空行，视为用户留出的补全槽位；根据上下文直接补写解释、总结、例子或下一步，不需标记不确定。
- Clip 保存：Safari 新剪藏一律先放到 `raw/unprocessed/` 根目录，不要求用户在保存时分类。开始 ingest 前，可为一组明确相关的已有资料新建临时子文件夹批次。
- 重点 Clip：标题（frontmatter `title`、一级标题或文件名）去除尾部空白后以字面 `*` 结尾，表示重点资料。重点 Clip 需阅读本地和相关外链图片、PDF、数据、视频和补充材料；普通 Clip 只读本地 Markdown 与 frontmatter，不展开正文链接或附件。参考文献链接始终不自动展开。
- 本地资源优先：重点 Clip 提到图片或附件时，先查其同目录及 `raw/` 内本地副本，再在必要时访问外链。

个性化方法与可安全修改的项目见 `docs/05-个性化设置.md`。改变底层流程、目录、状态机或 skills 时，必须同时记录 `wiki/meta/History/`。

## Raw 状态机

```text
unprocessed --ingest--> pending_review --用户明确批准--> processed
```

- `unprocessed`：新剪藏、附件或由已接受笔记复制而来的资料。
- `pending_review`：Codex 已建立来源页并更新 Wiki，等待用户审阅。
- `processed`：用户明确批准后，Markdown 与关联附件整组迁入 `raw/processed/`。
- 不得因 ingest 自动归档；不得因为“保持整洁”删除 Raw。

允许在 Markdown frontmatter 使用：`processing_status`、`reviewed_at`、`processed_at`、`processed_into`、`ingest_group`、`attachments`、`origin_note`、`note_approved_at`。附件不写 frontmatter，跟随关联 Markdown 状态。

## Ingest 与批准

1. 先读 `raw/index.md`、`wiki/index.md`、`wiki/log.md` 并扫描 `raw/unprocessed/`。
2. ingest 单元优先级：同一子文件夹批次 → 同名或 `attachments` 关联附件 → 相同 `ingest_group` → 用户指定组合 → 单篇 Markdown。
3. ingest 前先说明将处理哪些资料、内容判断和预计更新页面；无法判断类别时先问用户。
4. 每个单元在 `wiki/sources/` 创建/更新证据页，并按实际内容更新文献综合、实验方法或研究方向页面。
5. 更新 `wiki/index.md`、`wiki/log.md` 与 `raw/index.md` 后，才能把关联 Markdown 标为 `pending_review`；停止等待批准。
6. 仅在用户明确说“可以归档”“批准进入 processed”等后，迁移资料、修复旧 `raw/unprocessed/` 链接、更新索引和日志。

单批推荐 2–5 篇；过大批次先拆分。遇到目标路径冲突必须停止报告，不得自动覆盖或重命名。

## 知识图谱与页面规范

- `wiki/sources/` 是证据节点；其余三个主题目录是知识节点。
- 知识页关键结论优先链接本地来源页，例如 `[[sources/某来源#关键观点]]`；外部 URL 留在 Raw frontmatter 或来源页中，不作主图谱边。
- 推荐 frontmatter：通用字段 `type`、`status`、`topic`、`updated`；来源页可用 `raw_note`、`external_url`、`related_sources`；知识页可用 `supports`、`contradicts`、`related_sources`、`related_literature_synthesis`、`related_experimental_methods`、`related_research_directions`。
- 资料冲突必须记录，不能静默抹平。证据不足时标为待确认，不要写成确定事实。

## 笔记扩写与联动

- 用户要求整理 `notes/class/` 或 `notes/method/` 时，用 `expand-notes` 直接完善原文件；不要自动复制到 Raw。
- 用户检查、返修并明确接受某笔记扩写后，用 `note-approve` 创建 Raw 副本到 `raw/unprocessed/note-approve/YYYY-MM-DD-HHmm-原笔记名/`，保留原笔记不动。
- 后续该副本与网页 Clip 使用同一 ingest、审阅、归档状态机；来源页必须回链 `origin_note`。

## 索引、日志与底层变更

- `wiki/index.md` 是知识目录；`raw/index.md` 是队列与状态目录；`wiki/log.md` 是时间线。
- 每次 ingest、approve、note-approve、query 回填或 lint 都维护必要索引和日志。
- 改动规则、skills、目录、默认路径、状态机、权限或插件配置时，新建 `wiki/meta/History/YYYY-MM-DD-HHmm-主题.md`，并更新 `wiki/meta/History/index.md`。记录时间、旧设定、新设定、原因、影响和实际路径；历史只追加。

## 禁止事项

- 未经用户确认，不得迁移 `pending_review` Raw 到 `processed`。
- 不得改写 Raw 正文、删除冲突、把推测当事实，或只改正文而遗漏索引和状态。
- 不得擅自重组用户分类子文件夹或笔记大纲。
- 不要将个人身份信息、患者资料、未公开研究数据或人类基因组数据上传第三方服务；先要求本地脱敏版本。
