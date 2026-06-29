# SADS（单人 AI 软件开发系统）

## 概述

本仓库是一个用于单人 AI 驱动软件开发流程的执行工作区。

该系统用于将 ChatGPT 与 Codex App 结合，实现从需求分析到代码实现的完整开发闭环。

---

## 角色定义

- ChatGPT：产品架构师（需求分析 / 系统设计 / 任务拆解）
- Codex App：工程执行器（代码实现 / 测试 / 提交）
- GitHub：唯一事实源（状态 / 文档 / 代码）

---

## 核心原则

系统通过三类核心文件驱动：

- state/PROJECT_STATE.md → 当前阶段与控制状态
- tasks/TASK_QUEUE.md → Codex 可执行任务队列
- docs/ → 产品设计与系统规范

---

## 标准目录结构

```
docs/
  PRD.md            产品需求文档
  ARCHITECTURE.md   架构设计文档

tasks/
  TASK_QUEUE.md     任务队列（Codex执行）

state/
  PROJECT_STATE.md  项目状态控制
  ARTIFACT_INDEX.md 文档索引

src/               源代码目录
tests/             测试代码目录
```

---

## 工作流

1. ChatGPT 生成 PRD / 架构 / 任务拆解
2. 写入 GitHub 仓库
3. Codex App 读取 TASK_QUEUE.md
4. Codex 执行任务并提交代码
5. ChatGPT 基于 state 进行下一阶段决策

---

## 最小运行协议

PROJECT_STATE.md 控制系统流转：

- stage：Problem → Solution → MVP → Build → QA → Release
- status：READY / BLOCKED / DONE
- next_task：当前执行任务指针

---

## 系统约束

- 不允许在对话中直接执行代码
- 任务必须结构化、可执行
- GitHub 是唯一状态存储层
- Codex 不参与需求设计
- ChatGPT 不直接写代码

---

## 系统目标

构建一个稳定、低上下文成本、可长期运行的单人 AI 软件开发流水线。
