# Home

Top-level synthesis and orientation for this knowledge base.

## About

This wiki is incrementally built and maintained by an LLM agent. Raw sources are immutable; the wiki is the LLM's layer — summaries, entity pages, concept pages, cross-references, and evolving synthesis.

## Quick Links

- [Index](index.md) — catalog of all wiki pages
- [Log](log.md) — chronological activity record

## Current State

This wiki is focused on **Agent 架构设计**，特别是如何构建可扩展、可演进的 Agent 系统。当前核心主题围绕 [Anthropic](entities/Anthropic.md) 的 [Managed Agents](entities/Managed-Agents.md) 解耦架构展开。

### 核心洞见

1. **解耦是 Agent 系统扩展的基础** — [Brain-Hands-Session 解耦模型](concepts/brain-hands-session.md) 将 Agent 的推理、执行和记忆分离为可独立替换的组件
2. **接口应比实现更长寿** — [Meta-harness](concepts/meta-harness.md) 借鉴操作系统的抽象思路，为"尚未设想的程序"设计系统
3. **假设会随模型进化而过时** — [The Bitter Lesson](concepts/bitter-lesson.md) 和 [Context Anxiety](concepts/context-anxiety.md) 提醒我们：弥补模型缺陷的特定设计终将失效
4. **安全边界不可妥协** — 凭证永远不暴露在 [Sandbox](concepts/sandbox.md) 中
5. **Cattle > Pet** — [Pets vs Cattle](concepts/pets-vs-cattle.md) 在 Agent 系统中同样适用
6. **长时运行需要结构化交接** — [Long-Running Agent](concepts/long-running-agent.md) 无法依赖 context window 传递状态，[Initializer/Coding Agent 模式](concepts/initializer-coding-agent.md) 通过 progress file + feature list + git history 三重机制桥接 session
7. **增量推进胜过一次性完成** — [Feature List Pattern](concepts/feature-list-pattern.md) 将需求拆解为细粒度可验证项，一次做一个 feature，端到端测试后才标记完成

## Open Questions

- Meta-harness 的接口设计能否真正容纳未来未知的 harness 类型？
- 随着模型能力持续增长，harness 中的哪些逻辑可以完全消除？
- Context engineering 的最佳实践是否会收敛，还是会随模型进化持续变化？
- 单一通用 coding agent vs 多 agent 架构（测试/QA/清理 agent）哪个更优？
- Feature List Pattern 能否泛化到 Web 开发以外的领域（科研、金融建模）？
