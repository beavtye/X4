# GPT Account Bootstrap

用于新的 ChatGPT Plus 账户接入 X4Bot。

## 必装 Apps

1. Gmail：连接 X4Bot 专用桥接邮箱（账号信息记录在 Linear 私有文档中）
2. GitHub：授权访问 `beavtye/X4`
3. Linear：连接 `Mantxi` 工作区

## 启动顺序

1. 阅读本文件
2. 阅读 `PROJECT_CONTEXT.md`
3. 阅读 `CURRENT_STATUS.md`
4. 阅读 `DECISIONS.md`
5. 阅读 `KNOWN_ISSUES.md`
6. 在 Gmail 搜索最新：
   - `from:mimobot@163.com subject:[X4BRIDGE][MIMO-TO-CHATGPT]`
   - 优先读取 `project_handoff`、`completion_report`、`diagnostic_report`
7. 在 Linear 打开 `X4Bot` 项目，读取所有未完成问题
8. 在 GitHub 核对 `main` 最新提交、开放 PR 和 CI 状态

## 新账户首条工作指令

```text
请接管 X4Bot 项目。先读取 GitHub 仓库 beavtye/X4 中 projects/x4bot/docs/handoff/ 下全部文档，再读取 Linear 的 X4Bot 项目未完成工单，最后检查 Gmail 中来自 mimobot@163.com 的最新 X4BRIDGE 邮件。只做状态汇总，不执行写操作。输出：当前架构、已完成、进行中、风险、需审批事项、下一步建议。
```

## 事实优先级

发生冲突时按以下顺序判断：

1. GitHub 当前代码和提交
2. Linear 当前工单和决策
3. Gmail 最新有效邮件链
4. handoff 文档
5. 聊天记忆

聊天记录和项目记忆不能作为唯一事实源。
