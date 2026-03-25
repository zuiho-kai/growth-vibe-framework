# 贡献指南

感谢你对 OpenClaw 社区项目的兴趣！这是一个实验性的 AI 社会模拟项目，我们欢迎所有形式的贡献。

## 🌟 为什么参与这个项目？

- **前沿探索**: 探索 AI Agent 社会模拟的可能性
- **技术挑战**: 涉及 LLM、向量数据库、实时通信、经济系统等多个技术领域
- **开放协作**: 采用 AI 辅助开发模式，人类 + AI 协作
- **有趣**: 看着 AI 像人类一样生活、工作、社交，本身就很有趣

## 🎯 参与方式

### 1. 代码贡献

#### 前端开发
**技能要求**: React, TypeScript, WebSocket, CSS

**可以做的事情**:
- 🎨 优化现有 UI 组件
- 📊 经济数据可视化（图表）
- 🗺️ 2D 地图可视化（PixiJS）
- 🎨 引入前端组件库（shadcn/ui 或 Radix UI）
- 🔄 WebSocket 断线自动重连

**入门任务**:
- 优化 Agent 卡片样式
- 添加消息时间戳显示
- 实现消息搜索功能

#### 后端开发
**技能要求**: Python, FastAPI, SQLite, LLM API

**可以做的事情**:
- 🔧 M6 Agent CLI 运行时（持久进程 + 上网 + 工具扩展）
- 🔧 修复技术债务（分页、断线重连等）
- 📊 优化数据库查询性能
- 🧪 补充测试覆盖
- 🐳 Docker 生产级配置

**入门任务**:
- 添加 Agent CRUD 分页功能
- 实现 GET /api/messages 增量拉取
- 优化 WebSocket 心跳机制

#### 测试
**技能要求**: pytest, 测试思维

**可以做的事情**:
- ✅ 编写单元测试
- 🔗 编写集成测试
- 🎭 补充端到端测试场景
- 🐛 发现并报告 bug
- 📊 性能测试和压力测试

**入门任务**:
- 为现有功能补充测试用例
- 编写边界条件测试
- 性能测试

### 2. 设计贡献

#### 游戏设计
**可以做的事情**:
- 🎮 设计工作岗位和收入体系
- 💰 平衡经济系统（信用点定价、通胀控制）
- 🎯 设计悬赏任务类型
- 🏙️ 设计城市模拟玩法

#### UI/UX 设计
**可以做的事情**:
- 🎨 设计 UI 原型（Figma）
- 🖼️ 设计图标和插画
- 📱 优化移动端体验

### 3. 文档贡献

**可以做的事情**:
- 📝 完善 API 文档
- 📖 编写使用教程
- 🌍 翻译文档（英文）
- 📊 编写架构分析文档

**入门任务**:
- 补充 API 接口示例
- 编写快速开始指南
- 整理常见问题 FAQ

### 4. 数据分析

**可以做的事情**:
- 📊 分析 AI 行为模式
- 💰 分析经济系统平衡性
- 🧠 分析记忆系统效果
- 📈 可视化项目数据

## 🚀 开始贡献

### 1. 环境搭建

```bash
# 克隆仓库
git clone https://github.com/zuiho-kai/bot_civ.git
cd bot_civ

# 后端环境
cd server
pip install -r requirements.txt
cp .env.example .env
# 编辑 .env 填写 API keys

# 前端环境
cd ../web
npm install

# 运行测试
cd ../server
pytest tests/ -v
```

### 2. 了解项目

**必读文档**:
- [README.md](README.md) - 项目概览
- [PRD.md](docs/PRD.md) - 产品需求
- [ROADMAP.md](ROADMAP.md) - 开发路线图
- [TDD-M2](docs/specs/SPEC-001-聊天功能/TDD-M2-记忆与经济.md) - 当前阶段技术设计

**推荐阅读**:
- [讨论记录](docs/discussions.md) - 设计决策过程
- [API 契约](docs/api-contract.md) - 前后端接口规范

### 3. 选择任务

查看 [ROADMAP.md](ROADMAP.md) 找到感兴趣的功能：
- ✅ 已完成 - 可以优化或重构
- 🚧 进行中 - 可以协助完成
- 📋 待开始 - 可以认领开发

### 4. 提交代码

```bash
# 创建分支
git checkout -b feature/your-feature-name

# 开发 + 测试
# ...

# 提交
git add .
git commit -m "feat: your feature description"
git push origin feature/your-feature-name

# 创建 Pull Request
```

## 📋 代码规范

### Python (后端)

```python
# 使用 type hints
async def save_memory(
    self,
    agent_id: int,
    content: str,
    memory_type: str,
    db: AsyncSession
) -> Memory:
    pass

# 使用 docstring
def search_memories(query: str, agent_id: int, top_k: int = 5):
    """搜索该 agent 的个人记忆 + 公共记忆

    Args:
        query: 搜索查询
        agent_id: Agent ID
        top_k: 返回结果数量

    Returns:
        list: 记忆列表
    """
    pass

# 使用 async/await
async def handle_message(message: dict):
    result = await some_async_function()
    return result
```

### TypeScript (前端)

```typescript
// 使用 TypeScript 类型
interface Agent {
  id: number;
  name: string;
  credits: number;
}

// 使用函数式组件 + Hooks
const AgentCard: React.FC<{ agent: Agent }> = ({ agent }) => {
  const [expanded, setExpanded] = useState(false);

  return (
    <div className={styles.card}>
      {/* ... */}
    </div>
  );
};

// 使用 CSS Modules
import styles from './AgentCard.module.css';
```

### 测试

```python
# 测试文件命名: test_*.py
# 测试函数命名: test_*

@pytest.mark.asyncio
async def test_economy_check_quota():
    """测试额度检查逻辑"""
    # Arrange
    agent = create_test_agent(credits=5, quota_used_today=10)

    # Act
    result = await economy_service.check_quota(agent.id, "chat", db)

    # Assert
    assert result.allowed == True
```

### Commit 规范

使用 [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: 添加悬赏任务页面
fix: 修复记忆检索 bug
docs: 更新 API 文档
test: 添加经济系统测试
refactor: 重构唤醒引擎
perf: 优化向量搜索性能
chore: 更新依赖版本
```

## 🤖 AI 辅助开发

本项目采用 AI 辅助开发模式（Claude Code）：

- 📝 所有设计讨论记录在 `docs/discussions/`
- 📊 进展记录在 `claude-progress.txt` 和 `server/progress.md`
- 🤝 人类 + AI 协作，AI 负责实现，人类负责决策

**如何与 AI 协作**:
1. 在 `docs/discussions/` 创建讨论文档
2. 描述需求和设计思路
3. AI 会基于讨论实现功能
4. 人类 review 代码并提出改进

## 💬 交流渠道

- **GitHub Issues**: 报告 bug、提出功能建议
- **GitHub Discussions**: 技术讨论、设计讨论
- **Pull Requests**: 代码 review、功能讨论

## 🎯 当前优先级

根据 [ROADMAP.md](ROADMAP.md)，当前优先级：

**高优先级** (M6 Agent CLI 运行时):
1. Agent 持久进程（后台常驻运行）
2. Agent 上网能力
3. 任意工具调用扩展

**中优先级** (技术债务):
1. Agent CRUD 分页
2. WebSocket 断线重连
3. 消息增量拉取（since_id）
4. Docker Compose 完善（生产级配置）
5. 引入前端组件库（shadcn/ui 或 Radix UI）

**低优先级** (未来):
1. 2D 地图可视化（PixiJS 集成）
2. Agent 自主移动系统
3. 社交网络（关系图谱、好友系统）

## 📜 行为准则

- 🤝 尊重所有贡献者
- 💬 友好、建设性的讨论
- 🎯 专注于项目目标
- 📝 清晰的沟通
- 🧪 保证代码质量（测试 + review）

## ❓ 常见问题

### Q: 我不熟悉 LLM API，可以参与吗？
A: 可以！前端开发、测试、文档、游戏设计都不需要 LLM 知识。

### Q: 我只能贡献一点点时间，可以吗？
A: 当然！任何贡献都是有价值的，哪怕只是修复一个 typo。

### Q: 我有个想法，但不确定是否合适？
A: 在 GitHub Discussions 或 Issues 提出来讨论！

### Q: 代码被 AI 写的，我的贡献还有意义吗？
A: 非常有意义！AI 只是工具，设计决策、代码 review、测试验证都需要人类。

### Q: 我可以用这个项目做商业化吗？
A: 项目采用 MIT License，可以自由使用。但请注意 LLM API 的使用条款。

---

**感谢你的贡献！让我们一起构建有趣的 AI 社会模拟项目！** 🎉
