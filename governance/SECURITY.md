# 仓库安全规则

## 禁止提交

- API Key、Token、Cookie、授权码、密码
- `.env`、真实配置文件、Credential Manager 导出物
- Gmail / 163 / GitHub / Linear 凭据
- QQ 私聊、群聊原文、成员数据、NapCat 运行数据
- AstrBot 数据库、日志、缓存、会话和运行态 state
- AgentBridge inbox/outbox/sent/processed/failed 内容
- 原始故障包、浏览器缓存和临时文件

## 允许提交

- 脱敏后的配置模板
- 变量名、用途和获取步骤
- 不含真实数据的测试夹具
- 结构化审计结论
- 部署、恢复和验证脚本

## 提交前检查

1. `git status --short`
2. 检查 `.gitignore`
3. 运行 secret scan
4. 检查新增的大文件、数据库、日志和压缩包
5. 邮件报告只写命中类型和文件路径，不写秘密原文

## 泄漏处理

发现秘密进入 Git 历史时：

1. 立即停止 push
2. 先轮换或撤销对应凭据
3. 记录受影响路径和提交
4. 经用户批准后再清理历史和 force push
5. 清理后重新扫描

## 仓库可见性

包含 X4Bot 实现、部署和运维资料的仓库必须保持 Private。公开发布需另建专用仓库，并进行独立脱敏审查。
