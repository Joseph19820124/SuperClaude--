# 故障排除指南

## 🔧 常见安装问题

### 问题1: 权限错误
```bash
Error: No write permission for ~/.claude/
```

**解决方案：**
```bash
# 检查目录权限
ls -la ~/.claude/

# 修复权限
sudo chown -R $USER:$USER ~/.claude/
chmod -R 755 ~/.claude/
```

### 问题2: 找不到 Claude Code
```bash
claude: command not found
```

**解决方案：**
1. 确保已安装 Claude Code：
   ```bash
   # 检查 Claude Code 是否已安装
   which claude
   ```

2. 如果未安装，请访问 [Anthropic 官方文档](https://docs.anthropic.com) 获取安装指南

### 问题3: Git 未安装
```bash
git: command not found
```

**解决方案：**
```bash
# Ubuntu/Debian
sudo apt update && sudo apt install git

# macOS
brew install git

# 或使用 Xcode Command Line Tools
xcode-select --install
```

### 问题4: 安装脚本失败
```bash
Error: This script must be run from the SuperClaude directory
```

**解决方案：**
```bash
# 确保在正确的目录中
pwd
ls -la

# 应该能看到 CLAUDE.md 和 install.sh 文件
# 如果没有，重新克隆仓库
git clone https://github.com/NomenAK/SuperClaude.git
cd SuperClaude
./install.sh
```

## 🐛 使用问题

### 问题1: 命令不识别
```bash
/user:analyze --code
# 没有反应或提示错误
```

**解决方案：**
```bash
# 检查配置文件是否存在
ls ~/.claude/
ls ~/.claude/commands/

# 重新加载配置
/user:load

# 或重新安装
cd SuperClaude
./install.sh --force
```

### 问题2: 人格模式无效
```bash
/persona:architect
# 没有切换效果
```

**解决方案：**
```bash
# 检查 PERSONAS.md 文件
cat ~/.claude/PERSONAS.md

# 重新安装如果文件缺失
./install.sh --update
```

### 问题3: 检查点功能不工作
```bash
/user:git --checkpoint
# 提示 Git 错误
```

**解决方案：**
```bash
# 初始化 Git 仓库（如果项目未使用 Git）
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"

# 或在现有 Git 项目中使用
cd your-git-project
claude
```

## 🔄 重新安装

如果遇到无法解决的问题，可以完全重新安装：

```bash
# 1. 卸载现有安装
cd SuperClaude
./install.sh --uninstall

# 2. 清理残留文件（可选）
rm -rf ~/.claude/

# 3. 重新安装
./install.sh

# 4. 验证安装
claude
/user:load
```

## 🆘 获取帮助

如果以上解决方案都无效：

1. **检查原项目 Issues**：[SuperClaude Issues](https://github.com/NomenAK/SuperClaude/issues)

2. **查看安装日志**：
   ```bash
   ./install.sh 2>&1 | tee install.log
   ```

3. **提供系统信息**：
   ```bash
   # 操作系统信息
   uname -a
   
   # Bash 版本
   bash --version
   
   # Git 版本
   git --version
   
   # Claude Code 版本（如果可用）
   claude --version
   ```

4. **加入社区讨论**：[SuperClaude Discussions](https://github.com/NomenAK/SuperClaude/discussions)

## 📋 快速诊断检查清单

- [ ] 已安装 Claude Code
- [ ] 已安装 Git
- [ ] 在 SuperClaude 目录中运行安装脚本
- [ ] 有 ~/.claude/ 目录的写权限
- [ ] ~/.claude/ 目录包含所需文件：
  - [ ] CLAUDE.md
  - [ ] RULES.md
  - [ ] PERSONAS.md
  - [ ] MCP.md
  - [ ] commands/ 目录
  - [ ] commands/shared/ 目录
- [ ] 在 Git 仓库中使用 Claude Code（检查点功能需要）

完成所有检查后，SuperClaude 应该能正常工作。