# SADS 仓库结构治理规范（强约束）

## 一、核心原则

本仓库属于 Solo AI Dev System（SADS），结构稳定性优先级高于开发便利性。

必须遵守：

1. 仓库目录结构一旦确定，默认不可变更
2. 新增内容必须归类到既有目录，不得随意新增顶级目录
3. 架构调整必须显式走“架构变更流程”

---

## 二、允许的顶级目录（唯一合法集合）

```
docs/      产品设计与需求文档
state/     项目状态控制
tasks/     Codex 可执行任务
src/       源代码
tests/     测试代码
```

⚠️ 禁止新增任何顶级目录（除非经过架构变更流程批准）

---

## 三、目录职责边界

### docs/
仅允许：
- PRD
- 架构设计
- UX设计
- 产品定义

禁止：
- 任务
- 状态
- 代码

---

### state/
仅允许：
- PROJECT_STATE.md
- ARTIFACT_INDEX.md

职责：系统运行状态与阶段控制

---

### tasks/
仅允许：
- TASK_QUEUE.md
- Codex可执行任务拆分文件

---

### src/
仅允许业务代码

---

### tests/
仅允许测试代码

---

## 四、架构变更流程（强约束）

任何以下行为必须触发架构评审：

- 新增顶级目录
- 修改目录职责
- 删除现有目录

流程：

1. ChatGPT 输出 ARCHITECTURE_CHANGE.md
2. 人工确认
3. 才允许 Codex 执行

---

## 五、Codex约束

Codex 禁止：
- 自建顶级目录
- 重构 docs/tasks/state
- 修改系统结构定义

Codex 仅允许：
- 修改 src/
- 修改 tests/
- 按 tasks 执行开发

---

## 六、ChatGPT约束

ChatGPT 禁止：
- 绕过 tasks 直接要求编码
- 跳过 state 更新流程

---

## 七、优先级

state/ > tasks/ > docs/ > src/ > tests/

---

## 八、系统目标

在保证结构稳定的前提下，实现单人 AI 软件开发流水线的长期运行能力。
