# SuperClaude 中文操作指南

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-4.0.0-blue.svg)](https://github.com/NomenAK/SuperClaude)

**一个轻量级框架，将通用的 Claude Code 转换为您的专业开发合作伙伴 - 无需外部工具，无需复杂设置，仅需纯配置魔法。**

## 📖 项目介绍

SuperClaude 是一个增强 Claude Code 功能的配置框架。它解决了以下问题：
- Claude Code 过于通用，缺乏专业性
- 在调试过程中经常丢失上下文
- 每个项目都需要重复相同的指令
- 希望 AI 能理解您的编码风格
- 冗长的回复消耗了大量 token

## ✨ 主要特性

### 🔄 **永不丢失上下文**
基于 Git 的检查点系统，让您可以回到对话中的任何时点。

### 📚 **智能文档系统**
使用 token 优化模板自动生成文档。项目文档保存在 `/docs` 目录，而 Claude 的工作笔记保存在 `/.claudedocs` 目录。

### 🎭 **9 种即时人格模式**
一个命令即可切换 Claude 的整个思维模式：
- `architect` - 大局观系统设计模式
- `frontend` - 像素级完美 UI 强迫症模式  
- `security` - 偏执威胁建模模式
- `analyzer` - 福尔摩斯调试模式
- `qa` - 极致bug猎手模式
- `performance` - 性能恶魔模式
- `refactorer` - 代码美化师模式
- `backend` - 性能强迫症模式
- `mentor` - 耐心导师模式

### ⚡ **18 个强力命令**
为实际工作提供真正的快捷方式

### 🧠 **智能集成**
- **Context7** 即时查找库文档
- **Sequential** 复杂问题的逐步思考
- **Magic** 生成真正符合您风格的 UI 组件
- **Puppeteer** 在真实浏览器中测试一切

## 🚀 零摩擦安装

### 前置要求

1. **Claude Code** - 您需要先安装 Anthropic 的 Claude Code 工具
2. **Git** - 用于版本控制和检查点功能
3. **Bash** - 运行安装脚本

### 安装步骤

#### 步骤 1: 克隆仓库
```bash
git clone https://github.com/NomenAK/SuperClaude.git
cd SuperClaude
```

#### 步骤 2: 运行安装脚本
```bash
# 默认安装到 ~/.claude/
./install.sh

# 或者安装到自定义位置
./install.sh --dir /opt/claude          # 系统级安装
./install.sh --dir ./project-claude    # 项目级安装
```

#### 步骤 3: 验证安装
安装完成后，您会看到类似以下的输出：
```
✓ SuperClaude installed successfully!

Next steps:
1. Open any project with Claude Code
2. Try a command: /user:analyze --code
3. Activate a persona: /persona:architect
```

### 安装选项说明

| 选项 | 说明 |
|------|------|
| `--dir <目录>` | 安装到自定义目录（默认：~/.claude/） |
| `--force` | 跳过确认提示（用于自动化） |
| `--update` | 更新现有安装（保留自定义配置） |
| `--uninstall` | 从指定目录移除 SuperClaude |
| `-h, --help` | 显示帮助信息 |

## 💡 快速入门

### 第一次使用

1. **打开任何项目**
   ```bash
   cd your-project
   claude
   ```

2. **尝试第一个命令**
   ```bash
   /user:analyze --code
   ```

3. **激活一个人格模式**
   ```bash
   /persona:architect
   ```

### 常用工作流程示例

#### 新项目流程
```bash
/persona:architect
/user:design --api --ddd     # 从领域驱动设计开始
/user:estimate --detailed    # 了解您要构建的内容
/persona:backend
/user:build --api --tdd      # 第一次就正确构建
```

#### 故障排除流程
```bash
/persona:analyzer
/user:troubleshoot --investigate --prod
/user:analyze --profile      # 找到真正的瓶颈
/persona:performance
/user:improve --performance --threshold 90%
```

#### 美化界面流程
```bash
/persona:frontend
/user:build --react --magic  # AI 生成的组件
/user:test --e2e --pup       # 在真实浏览器中查看效果
/user:improve --quality      # 抛光直到闪亮
```

## 🎭 人格模式详解

| 人格 | 超能力 | 何时激活 |
|------|--------|----------|
| **architect** | 看到大局 | 需要可扩展的系统设计时 |
| **frontend** | UX 完美主义者 | 需要用户喜爱的界面时 |
| **backend** | 性能强迫症 | 需要永不失败的 API 时 |
| **security** | 专业偏执狂 | 需要防弹代码时 |
| **analyzer** | 根因探测器 | 需要解决无法解决的问题时 |
| **qa** | 极致 bug 猎手 | 需要捕获一切的测试时 |
| **performance** | 速度恶魔 | 每毫秒都很重要时 |
| **refactorer** | 代码美化师 | 需要简化复杂代码时 |
| **mentor** | 耐心老师 | 需要理解而不只是复制时 |

## 🛠️ 核心命令详解

### 分析命令 (`/user:analyze`)
```bash
/user:analyze --code         # 代码质量分析
/user:analyze --security     # 安全审计
/user:analyze --performance  # 性能分析
/user:analyze --structure    # 架构分析
```

### 构建命令 (`/user:build`)
```bash
/user:build --react          # React 应用
/user:build --api            # API 服务
/user:build --component      # 组件库
/user:build --fullstack      # 全栈应用
```

### 测试命令 (`/user:test`)
```bash
/user:test --unit            # 单元测试
/user:test --e2e             # 端到端测试
/user:test --integration     # 集成测试
/user:test --performance     # 性能测试
```

### 改进命令 (`/user:improve`)
```bash
/user:improve --performance  # 性能优化
/user:improve --security     # 安全加固
/user:improve --quality      # 代码质量
/user:improve --accessibility # 可访问性
```

### Git 命令 (`/user:git`)
```bash
/user:git --checkpoint       # 创建检查点
/user:git --rollback         # 回滚到检查点
/user:git --branch           # 创建新分支
/user:git --merge            # 合并分支
```

## 🔧 高级功能

### 思考模式控制
```bash
"think about X"              # 标准分析
"think hard about Y"         # 架构级深度
"ultrathink Z"               # 考虑一切的时候
```

### 智能工具控制
```bash
--c7           # 强制文档查找
--seq          # 强制逐步推理
--magic        # 强制 UI 组件生成
--no-mcp       # 仅使用原生工具
--all-mcp      # 厨房水槽模式
```

### 检查点系统
SuperClaude 的 Git 集成检查点系统让您永远不会丢失工作进度：

1. **创建检查点**
   ```bash
   /user:git --checkpoint "开始重构前的安全点"
   ```

2. **查看检查点**
   ```bash
   /user:git --list
   ```

3. **回滚到检查点**
   ```bash
   /user:git --rollback checkpoint-name
   ```

## 📁 文件结构

安装后，SuperClaude 会在指定目录创建以下结构：

```
~/.claude/
├── CLAUDE.md              # 核心配置和行为
├── RULES.md               # 工程标准和实践
├── PERSONAS.md            # 9 种专业思维模式
├── MCP.md                 # 智能工具编排
├── commands/              # 18 个命令
│   ├── analyze.md
│   ├── build.md
│   ├── improve.md
│   ├── test.md
│   └── ...
└── commands/shared/       # 26 个共享资源
    ├── patterns.yml
    ├── templates.yml
    └── ...
```

## 🚀 实际使用场景

### 场景 1: 调试生产问题
```bash
# 切换到分析师模式
/persona:analyzer

# 开始故障排除
/user:troubleshoot --prod --investigate

# 深度分析
/user:analyze --logs --performance --security

# 创建解决方案检查点
/user:git --checkpoint "找到解决方案前"

# 实施修复
/user:improve --performance --hotfix
```

### 场景 2: 开发新功能
```bash
# 切换到架构师模式进行设计
/persona:architect
/user:design --feature --scalable

# 切换到后端开发模式
/persona:backend
/user:build --api --tdd

# 切换到前端模式创建界面
/persona:frontend
/user:build --component --responsive

# 综合测试
/persona:qa
/user:test --e2e --complete
```

### 场景 3: 代码重构
```bash
# 创建重构前检查点
/user:git --checkpoint "重构前的稳定版本"

# 切换到重构师模式
/persona:refactorer

# 分析现有代码
/user:analyze --structure --complexity

# 执行重构
/user:improve --maintainability --clean

# 验证重构结果
/user:test --regression --performance
```

## ⚡ 性能优化

SuperClaude 提供 70% 的 token 减少，具体通过以下方式实现：

1. **UltraCompressed 模式** - 去除不必要的 token 而不失清晰度
2. **智能上下文管理** - 只保留相关信息
3. **优化的命令结构** - 减少重复指令
4. **高效的人格切换** - 快速模式转换

## 🛟 故障排除

### 安装问题
```bash
# 重新运行安装（幂等的）
./install.sh

# 查看安装选项
./install.sh --help

# 强制重新安装
./install.sh --force
```

### 命令不工作
```bash
# 检查安装的命令
ls ~/.claude/commands/

# 重新加载配置
/user:load
```

### 权限问题
```bash
# 检查目录权限
ls -la ~/.claude/

# 修复权限
chmod -R 755 ~/.claude/
```

## 🔄 更新和维护

### 更新 SuperClaude
```bash
cd SuperClaude
git pull
./install.sh --update
```

### 备份配置
```bash
# 手动备份
cp -r ~/.claude/ ~/.claude.backup.$(date +%Y%m%d)

# 安装时自动备份
./install.sh  # 会自动创建备份
```

### 卸载
```bash
./install.sh --uninstall
```

## 🤝 贡献和社区

SuperClaude 是 MIT 许可的开源项目，由开发者为开发者构建。我们欢迎：

- 专门工作流程的新人格模式
- 解决日常痛点的命令
- 使 Claude Code 更智能的模式
- 推动边界的想法

## 📊 效果对比

| 功能 | 没有 SuperClaude | 使用 SuperClaude |
|------|------------------|------------------|
| **上下文** | 错误后丢失 | Git 检查点保留一切 |
| **人格** | 通用回复 | 专业思维模式 |
| **Token** | 冗长输出 | 减少 70%，相同信息 |
| **文档** | "我认为这样工作" | 总是找到官方来源 |
| **工作流** | 重复指令 | 一个命令，完整流程 |
| **质量** | 希望最好的结果 | 基于证据的标准 |

## 🎯 适用人群

**完美适合如果您：**
- ✅ 希望在项目间获得一致的 AI 协助
- ✅ 重视证据胜过意见
- ✅ 需要专业化思维模式
- ✅ 关心 token 效率
- ✅ 喜欢开箱即用的工具

**跳过如果您：**
- ❌ 偏好完全手动控制
- ❌ 不经常使用 Claude Code
- ❌ 满足于通用 AI 回复

## 🚦 2 分钟快速开始

1. **安装**
   ```bash
   git clone https://github.com/NomenAK/SuperClaude.git && cd SuperClaude && ./install.sh
   ```

2. **试用**
   ```bash
   /user:analyze --code        # 看看它能找到什么
   /persona:architect          # 尝试新的思维方式
   ```

3. **深入探索**
   - 探索命令：`/user:load`
   - 阅读指南：`~/.claude/commands/`
   - 加入社区：[讨论区](https://github.com/NomenAK/SuperClaude/discussions)

## 📞 获得帮助

- **安装问题？** 再次运行 `./install.sh` - 它是幂等的
- **命令无效？** 检查 `ls ~/.claude/commands/`
- **想要贡献？** 查看原项目的 CONTRIBUTING.md
- **发现 bug？** 在原项目[开启 issue](https://github.com/NomenAK/SuperClaude/issues)

## 🔗 相关链接

- [原项目仓库](https://github.com/NomenAK/SuperClaude)
- [Claude Code 官方文档](https://docs.anthropic.com)
- [项目讨论区](https://github.com/NomenAK/SuperClaude/discussions)

---

**SuperClaude v4.0.0 - 因为通用 AI 助手已经不够好了。**

*本指南由 Claude 根据原项目文档翻译和整理，如有疑问请参考原英文文档。*