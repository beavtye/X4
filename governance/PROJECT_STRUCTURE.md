# 项目结构治理规则

## 1. 顶层目录

仅允许以下顶层目录：

- `projects/`：独立项目
- `shared/`：跨项目复用内容
- `governance/`：仓库级治理规则
- `.github/`：GitHub 工作流与模板

未经 ChatGPT 明确批准，不得新增其他顶层目录。

## 2. 项目目录标准

每个项目位于 `projects/<project-slug>/`，并遵循：

```text
projects/<project-slug>/
├─ README.md
├─ PROJECT_MANIFEST.yaml
├─ src/                   # 正式源代码
├─ scripts/               # 运维、迁移、诊断脚本
├─ tests/                 # 自动化测试
├─ config/                # 安全配置模板，禁止真实凭据
├─ deploy/                # 部署、恢复、验证脚本
├─ docs/
│  ├─ architecture/
│  ├─ operations/
│  ├─ deployment/
│  └─ handoff/
├─ manifests/             # 版本、校验和、组件清单
└─ tools/                 # 项目专用工具
```

空目录不提交；使用目录内 `README.md` 说明用途。

## 3. 文件归类矩阵

| 内容 | 路径 |
|---|---|
| 正式业务代码 | `src/` |
| 一次性诊断脚本 | `scripts/diagnostics/` |
| 数据迁移脚本 | `scripts/migrations/` |
| Windows 计划任务脚本 | `scripts/scheduled-tasks/` |
| 配置样例 | `config/*.example.*` |
| 架构说明 | `docs/architecture/` |
| 运维手册 | `docs/operations/` |
| 部署与恢复 | `docs/deployment/` |
| GPT/Mimo 交接 | `docs/handoff/` |
| 自动化测试 | `tests/` |
| 临时输出、日志、数据库 | 不提交 |

## 4. Mimo 权限边界

Mimo 可以：

- 在已指定项目目录内创建和修改实现文件
- 按任务要求增加测试和文档
- 提交变更报告

Mimo 不可以自行：

- 新增顶层目录
- 移动或重命名整个模块
- 把运行态文件塞入源码目录
- 把多个不相关功能堆进同一脚本
- 改变 `PROJECT_MANIFEST.yaml` 中的所有权和目录规则
- 推送凭据、日志、聊天原文或数据库

结构调整必须先提交提案，由 ChatGPT 审核。

## 5. 新项目创建

复制 `projects/_template/`，替换项目名和负责人，先提交结构再填充实现。禁止直接在仓库根目录堆文件。
