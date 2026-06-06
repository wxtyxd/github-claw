# memory/patterns.md - 可复用的工作模式

> 本文档记录已验���的工作模式、最佳实践和可复用的方法论。这是 AI 助手的"技能库"。

---

## 📋 工作模式清单

### 模式 1: 任务启动检查清单
**适用场景**：开始新任务时

- [ ] 查阅 `AGENTS.md` 确认当前角色和上下文
- [ ] 查阅 `PROGRESS.md` 了解任务状态
- [ ] 如需要，查阅 `memory/context.md` 和 `memory/daily/` 获取历史信息
- [ ] 在 `PROGRESS.md` 中添加或更新任务记录
- [ ] 与用户确认任务目标和验收标准

**收益**：快速上下文切换，避免重复工作

---

### 模式 2: 每日日志记录
**适用场景**：每次对话结束时

**模板**（`memory/daily/YYYY-MM-DD.md`）：
```markdown
# 2026-06-06 日志

## 完成的工作
- 任务名 1：具体描述
- 任务名 2：具体描述

## 遇到的问题
- 问题 1：原因和解决方案
- 问题 2：原因和解决方案

## 学到的东西
- 学习点 1
- 学习点 2

## 明天的计划
- [ ] 待做 1
- [ ] 待做 2
```

**收益**：记录日常进展，便于回溯，发现规律

---

### 模式 3: 决策记录
**适用场景**：遇到架构/工作流选择时

**记录格式**（在 `memory/context.md` 中）：
```markdown
## 决策：[决策名称]
**时间**：YYYY-MM-DD  
**背景**：为什么需要这个决策  
**选项**：
1. 方案 A - 优点 / 缺点
2. 方案 B - 优点 / 缺点

**选择**：方案 A  
**理由**：主要原因  
**结果**：实施后的影响
```

**收益**：避免重复讨论，保持决策一致性

---

### 模式 4: 文件变更总结
**适用场景**：完成对代码或文档的重大修改时

**Commit Message 格式**：
```
<type>: <short description>

<detailed explanation if needed>

Changes:
- 变更 1
- 变更 2

References:
- PROGRESS.md#Task-001
- memory/context.md#Decision-Name
```

**例子**：
```
docs: update AGENTS.md with daily log pattern

Added new section for daily log template and benefits.
This helps structure knowledge across multiple sessions.

Changes:
- Added "Pattern 2: Daily Log Recording" section
- Included template and benefits

References:
- PROGRESS.md#Task-001
```

**收益**：提高提交的可追溯性，便于代码审查

---

### 模式 5: 快速问题排查
**适用场景**：遇到错误或卡点时

步骤：
1. **记录现象**：错误消息、环境信息、重现步骤
2. **查询已知问题**：搜索 `memory/patterns.md` 和 `memory/daily/`
3. **尝试解决**：按 Copilot 的建议方案逐一尝试
4. **记录解决方案**：成功后，将方案保存到 `memory/snippets/` 或 `patterns.md`

**收益**：加快问题解决，积累经验库

---

## 🔧 代码片段模板

*(在 `memory/snippets/` 中维护)*

- `snippet-initial-checklist.md` - 任务启动检查清单
- `snippet-daily-log-template.md` - 日志模板
- `snippet-decision-template.md` - 决策记录模板
- `snippet-commit-message.md` - Commit Message 示例

---

## 📚 待补充的模式

- [ ] 代码审查流程
- [ ] 文档更新流程
- [ ] 遇到未知问题的调查方法
- [ ] 跨对话信息同步方法

---

*最后更新：2026-06-06 - 初始模式库建立*
