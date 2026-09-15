# Raw：原始资料层

将 Safari Web Clipper 的默认保存路径设为 `raw/unprocessed/`。不要在剪藏时为了分类改动保存路径；需要批处理时，Codex 可在 ingest 前把已有的相关资料组成临时子文件夹批次。

- `unprocessed/`：新资料。
- `processed/`：用户批准后的资料。
- `assets/`：无法与条目同放的资源。

请不要手工把资料从 `unprocessed` 移到 `processed`；让 Codex 在批准流程中同步修复索引和本地链接。
