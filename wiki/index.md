# Wiki Index

Catalog of all wiki pages, organized by category. Updated on every ingest.

## Overview

- [Home](home.md) — Top-level synthesis and orientation

## Entities

- [Anthropic](entities/Anthropic.md) — AI 安全公司，Claude 系列模型的开发商
- [Managed Agents](entities/Managed-Agents.md) — Anthropic 托管式 Agent 服务，解耦架构
- [Claude](entities/Claude.md) — Anthropic 的大语言模型系列
- [Justin Young](entities/Justin-Young.md) — Anthropic 工程师，Effective Harnesses for Long-Running Agents 作者

## Concepts

- [Session](concepts/session.md) — Agent 运行中的追加写入事件日志，持久化存储
- [Harness](concepts/harness.md) — Agent 的"大脑"，调用 Claude 并路由工具的循环
- [Sandbox](concepts/sandbox.md) — Agent 的"双手"，代码执行和文件编辑环境
- [Brain-Hands-Session 解耦模型](concepts/brain-hands-session.md) — 将 Agent 虚拟化为三个可独立替换的组件
- [Pets vs Cattle](concepts/pets-vs-cattle.md) — 基础设施运维的经典比喻，Pet 不可丢失 vs Cattle 可替换
- [Context Anxiety](concepts/context-anxiety.md) — Claude 感知 context window 将满时提前收工的行为
- [Meta-harness](concepts/meta-harness.md) — 不限定特定 harness 实现的系统设计
- [The Bitter Lesson](concepts/bitter-lesson.md) — Sutton：通用方法胜过特定设计
- [Context Engineering](concepts/context-engineering.md) — 管理 LLM context window 内容的工程实践
- [Long-Running Agent](concepts/long-running-agent.md) — 跨多个 context window 持续工作的 Agent
- [Initializer/Coding Agent 模式](concepts/initializer-coding-agent.md) — 双 Agent 分工：Initializer 搭建环境，Coding Agent 增量推进
- [Feature List Pattern](concepts/feature-list-pattern.md) — 用结构化 JSON 拆解需求并追踪完成状态

## Sources

- [Scaling Managed Agents: Decoupling](sources/Scaling-Managed-Agents-Decoupling.md) — Anthropic 工程博客：解耦 Brain、Hands、Session 的架构设计
- [Effective Harnesses for Long-Running Agents](sources/Effective-Harnesses-for-Long-Running-Agents.md) — Anthropic 工程博客：Initializer/Coding Agent 双模式解决跨 context window 长时运行问题

## Analyses

<!-- Analysis pages generated from queries, comparisons, etc. -->

## Topics

<!-- Topic pages that cut across categories -->
