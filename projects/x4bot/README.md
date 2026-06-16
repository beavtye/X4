# X4Bot

X4Bot 是基于 AstrBot、NapCat、WatchScan、Watchdog、Scrapling MCP 与 AgentBridge 的 QQ Bot 运维与自动化项目。

## 当前模块

- `src/`：正式代码
- `scripts/`：诊断、迁移和计划任务脚本
- `tests/`：自动化测试
- `config/`：安全配置模板
- `deploy/`：跨设备部署、恢复和验证
- `docs/architecture/`：架构与数据流
- `docs/operations/`：日常运维和故障处理
- `docs/deployment/`：设备迁移和恢复
- `docs/handoff/`：GPT/Mimo 交接资料
- `manifests/`：版本与校验和清单
- `tools/`：项目专用工具

## 管理边界

- ChatGPT 负责目录结构、项目框架、交接标准、任务拆解和验收。
- Mimo 只在明确指定路径内实现，不自行重构目录。
- 当前运行机器上的日志、数据库、聊天原文和凭据不进入仓库。

## 外部事实源

- GitHub：代码、部署脚本、正式文档
- Gmail：Mimo ↔ ChatGPT 任务与报告链
- Linear：待办、风险、审批和验收状态
