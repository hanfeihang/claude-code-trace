# Claude Code Trace

[English](README.md) | 中文

一款**纯浏览器、单 HTML 文件**的本地工具，用于可视化分析 Claude Code 生成的 Agent 会话日志（`.jsonl`）。

无需安装或构建步骤，解析与渲染均在浏览器本地完成，日志数据不会上传至任何服务器。

![Claude Code Trace 截图](images/show.png)

---

## 功能

### 时间线

以时间线形式展示 Agent 消息，区分用户输入、Assistant 响应、工具调用与客户端日志。单条消息可展开查看 `Thinking`、`Tool Call`、`Text`、`Tool Result` 等内容块。消息被聚合为 `User Call`、`LLM Call`、`Subagent Call` 等单元，并支持查看每次调用的 Token 用量。

### Subagent 展开

在 Main Session 时间线的工具调用处，可直接展开查看对应 Subagent Session 的完整时间线。

### 数据统计

顶栏汇总当前会话的总消息数、LLM 调用次数、工具调用次数、Subagent 数量、总 Token 及所用模型，便于快速评估一次 Agent 运行的规模与成本。

---

## 快速开始

1. 克隆仓库：
   ```bash
   git clone https://github.com/hanfeihang/claude-code-trace.git
   ```
2. 用 Chrome / Arc / Edge / Safari 打开 `claude-agent-trace.html`：
   ```bash
   cd claude-code-trace && open claude-agent-trace.html
   ```

---

## 适用场景

- 了解 Claude Code Agent 在运行过程中具体做了什么：每一次 LLM 调用的输入输出、Thinking 过程、工具调用顺序及返回结果
- 排查会话变慢或行为异常时，分析 Agent 的决策路径与潜在原因

---

## 技术说明

- **形态**：单文件静态页，无 npm 依赖，无后端，离线可用
- **隐私**：所有解析与渲染均在浏览器内存中完成，日志内容不会外传
