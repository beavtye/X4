# X4 Workspace

这是一个多项目仓库。所有项目必须放在 `projects/` 下，公共模板和通用工具放在 `shared/`，仓库级规则放在 `governance/`。

## 当前项目

- `projects/x4bot/` — AstrBot / NapCat / WatchScan / AgentBridge 项目

## 目录规则

```text
/
├─ projects/              # 独立项目
│  ├─ x4bot/
│  └─ _template/          # 新项目模板
├─ shared/                # 可复用模板、工具和公共文档
├─ governance/            # 命名、安全、交接和文件归类规则
├─ .gitignore
└─ README.md
```

## 管理原则

- ChatGPT 负责项目框架、目录规范、交接标准和验收口径。
- Mimo 负责按指定路径实现、测试和提交证据。
- Mimo 不得自行新增顶层目录、移动跨模块文件或改变项目结构。
- 所有凭据、聊天原文、数据库、日志和运行态文件禁止提交。
- 设备迁移与 GPT 账户切换必须依赖 GitHub、Gmail、Linear 三个外部事实源，而不是依赖某个聊天窗口的记忆。

详见 `governance/PROJECT_STRUCTURE.md` 与 `governance/SECURITY.md`。
