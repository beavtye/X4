# Current Status

> 由 ChatGPT 维护。Mimo 只提交事实和证据，不自行改写总体结论。

## 更新时间

- `2026-06-16 12:20 Asia/Shanghai`

## 系统状态

| 模块 | 状态 | 最近证据 | 备注 |
|---|---|---|---|
| AstrBot | last-known healthy | Gmail status report | 上次核验运行中；本轮未重新启动或停止 |
| NapCat / QQ | last-known healthy | Gmail status report | OneBot 上次核验可达 |
| WatchScan | degraded | Gmail completion report | 50 条错误 no_reply 已隔离为 data_source_incomplete；归档器出站消息修复尚未完成 |
| Watchdog | detect-only | Gmail completion report | `RECOVERY_ENABLED=False`，不会自动恢复 |
| AgentBridge | operational | Gmail completion report | Send / Receive 两个 10 分钟计划任务正常运行 |
| Scrapling MCP | last-known healthy | Gmail status report | 已加载 10 个工具；本轮未复测 |
| GitHub repository | framework initialized | GitHub | 多项目目录框架已建立；仓库可见性仍需确认并保持 Private |
| Mimo host Git tools | unavailable | Gmail security report | 本机未安装 git 和 gh，不能从该主机直接同步仓库 |

## 当前最高优先级

1. 完成归档器对 `接收 <-` 与 `发送 ->` 的双向解析。
2. 在临时数据上验证 WatchScan 可以出现 resolved，不再全部过期。
3. 保持 50 条历史误判隔离，不纳入真实 no_reply 指标。
4. 完成仓库安全核验，并确认仓库为 Private。
5. 制作跨设备部署包和 GPT 账户交接包。

## Linear 工单

- `MAN-5`：修复归档器与 WatchScan 关联
- `MAN-6`：隔离并重算错误 no_reply
- `MAN-7`：处理重复失败的归档计划任务
- `MAN-8`：实现 Watchdog 精确 PID 安全恢复
- `MAN-9`：GitHub 安全准备
- `MAN-10`：制作跨设备部署包
- `MAN-11`：制作 GPT 账户无缝交接包

## 需用户审批

- 重启 AstrBot、NapCat 或 QQ
- 杀进程
- 删除或禁用计划任务
- 修改正式数据库
- 开启 Watchdog 自动恢复
- 重写 Git 历史或 force push
- 发送 QQ 消息

## 最近有效交接

- `mimo-20260616-completion-report-001`
- `mimo-20260616-security-report-001`
- `mimo-20260616-diagnostic-report-001`

## 更新规则

- 代码和框架以 GitHub 为准。
- 工单、风险和审批以 Linear 为准。
- 运行状态以最新有效 Gmail 证据为准。
- 聊天记忆只能辅助，不能作为唯一事实源。
