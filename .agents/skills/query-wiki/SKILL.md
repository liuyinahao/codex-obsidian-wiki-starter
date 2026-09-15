---
name: query-wiki
description: 基于现有 Wiki 回答问题，优先本地来源证据，并按文献综合、实验方法和研究方向组织回填建议。
---

# query-wiki

读取 `AGENTS.md` 与 `wiki/index.md`，递归检索三个主题目录及必要的 `wiki/sources/`。

- 优先基于现有 Wiki 回答，不要绕过 Wiki 回到 Raw 做一次性总结。
- 关键判断链接到本地来源页或小节，清楚区分来源事实、当前综合判断和待验证问题。
- 若结果值得长期保留，建议或在用户语境明确时回填到最匹配的主题目录。
