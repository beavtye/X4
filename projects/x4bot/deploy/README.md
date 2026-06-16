# X4Bot Deployment

本目录由 ChatGPT 规划结构，Mimo 按指定文件实现。

目标文件：

- `bootstrap_windows.ps1`：新设备安装入口
- `export_runtime.ps1`：导出非敏感运行配置和清单
- `import_runtime.ps1`：导入部署包
- `verify_install.ps1`：验证 Python、AstrBot、NapCat、Scrapling、AgentBridge 和计划任务
- `task-templates/`：Windows 计划任务 XML 模板

规则：

- 不硬编码旧设备绝对路径
- 不打包凭据、日志、数据库、聊天原文和运行态 state
- 凭据通过交互式流程重新写入 Windows Credential Manager
- 每个脚本必须支持 `-WhatIf` 或 dry-run 等价模式
- 每次发布生成文件清单和 SHA256 manifest
