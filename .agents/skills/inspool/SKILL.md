---
name: inspool
description: 将高价值回答或阶段性结论回填为文献综合、实验方法或研究方向页面。
---

# inspool

用于把跨来源分析、阶段性结论或高价值问答沉淀回 Wiki。

1. 读取 `AGENTS.md` 与 `wiki/index.md`。
2. 选择最匹配的目标：比较/结论 → 文献综合；操作/排错 → 实验方法；灵感/假设 → 研究方向。
3. 创建或更新页面，加入必要双链与 frontmatter 关系字段；关键结论优先落到本地来源页。
4. 区分事实依据、综合结论与推测/开放问题；证据不足时不包装为最终结论。
5. 更新 `wiki/index.md`，并在 `wiki/log.md` 追加 `query` 或 `refactor` 日志。
