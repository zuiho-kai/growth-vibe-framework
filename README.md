# PID Vibe Code Framework

从 `D:\项目\a3\bot_civ` 中抽离出来的一套流程与知识框架，用作 PID 流程驱动的 vibe code 开发仓库。

这份仓库当前保留了原项目里最有价值的框架层资产：

- `CLAUDE.md`: 协作约束、门禁、阶段流程、代码与文档纪律
- `docs/workflows/`: 需求到实现到验收的完整流程
- `docs/personas/`: 多角色协作的人设与职责分工
- `docs/runbooks/error-books/`: 错题本、流程复盘、常见踩坑
- `docs/runbooks/`: 团队管理、模型选择、进度分层等操作手册
- `docs/templates/`: 文档模板
- `docs/tests/`: 测试文档示例
- `docs/specs/`、`docs/PRD.md`、`ROADMAP.md`: 来自原项目的参考样例，适合当范本使用

## 适合怎么用

1. 以 `CLAUDE.md` 作为协作总约束。
2. 以 `docs/workflows/development-workflow.md` 作为主流程。
3. 以 `docs/personas/roles.md` 决定多 Agent 分工。
4. 以 `docs/runbooks/error-books/` 作为错题本和流程回灌机制。
5. 在新项目中按需替换 `docs/PRD.md`、`docs/specs/`、`claude-progress.txt` 为你自己的业务内容。

## 建议的二次整理

- 把原项目特定的产品文档逐步替换成你自己的 PRD 和规格书
- 保留 `error-books` 和 `workflows` 作为稳定内核
- 如需更纯净的模板仓库，可以后续继续裁掉 `docs/images/` 和部分产品样例

## 来源说明

当前内容是从 `bot_civ` 文档层直接复制出来的第一版，可运行用、可继续瘦身。目标不是“空白模板”，而是一份带实战经验沉淀的框架基座。
