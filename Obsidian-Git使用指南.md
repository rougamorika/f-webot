# Obsidian Git 使用指南

## 📦 安装步骤

1. 在 Obsidian 中打开设置 → 第三方插件
2. 搜索并安装 "Obsidian Git"
3. 启用插件

## ⚙️ 推荐配置

### 自动备份设置

- **Vault backup interval**: `30` 分钟（每 30 分钟自动备份）
- **Commit message**: `自动备份: {{date}}`
- **Auto backup after file change**: ✅ 开启
- **Auto push**: ✅ 开启（重要！自动推送到 GitHub）

### 拉取设置

- **Auto pull interval**: `30` 分钟
- **Pull updates on startup**: ✅ 开启

## 🎯 重要说明

### Git 仓库位置问题

你的项目结构：
```
d:\fuckwebot\          ← Git 仓库根目录
├── .git/
├── content/           ← Obsidian 库位置
│   ├── index.md
│   └── ...
├── quartz/
└── quartz.config.ts
```

**问题**: Obsidian Git 插件需要在 Git 仓库的根目录工作。

### 解决方案：在 Obsidian 中打开整个项目

**推荐做法**：

1. 在 Obsidian 中打开 `d:\fuckwebot` 作为库（而不是 `content` 文件夹）
2. 这样 Obsidian Git 插件可以正常工作
3. 你的笔记仍然在 `content/` 文件夹中

**操作步骤**：

1. 打开 Obsidian
2. 点击 "打开其他库" → "打开文件夹作为库"
3. 选择 `d:\fuckwebot` 文件夹（不是 content 子文件夹）
4. 确认打开

这样你就可以：

- 在 `content/` 文件夹中编辑笔记
- 使用 Obsidian Git 插件自动提交和推送
- 自动更新 Vercel 网站

## 🎮 常用命令

安装插件后，你可以使用以下命令（按 `Ctrl+P` 打开命令面板）：

### 手动操作命令

- **Obsidian Git: Commit all changes** - 提交所有更改
- **Obsidian Git: Push** - 推送到 GitHub
- **Obsidian Git: Pull** - 从 GitHub 拉取更新
- **Obsidian Git: Commit and push** - 提交并推送（最常用）

### 快捷键设置（可选）

你可以在 Obsidian 设置中为常用命令设置快捷键：

1. 设置 → 快捷键
2. 搜索 "Obsidian Git"
3. 为 "Commit and push" 设置快捷键，例如 `Ctrl+Shift+G`

## 📋 推荐工作流程

### 自动化工作流（推荐）

配置好插件后，完全自动化：

1. **在 Obsidian 中编辑笔记** - 正常写作
2. **自动提交** - 插件每 30 分钟自动提交更改
3. **自动推送** - 自动推送到 GitHub
4. **自动部署** - Vercel 检测到更改，自动重新部署网站
5. **1-2 分钟后** - 网站更新完成

### 手动工作流

如果你想手动控制：

1. 在 Obsidian 中编辑笔记
2. 按 `Ctrl+P` 打开命令面板
3. 输入 "commit and push"
4. 回车执行
5. 等待 1-2 分钟，网站自动更新

## ⚠️ 注意事项

### 1. 文件夹结构

确保在 Obsidian 中打开 `d:\fuckwebot` 而不是 `content` 子文件夹。

### 2. .gitignore 配置

Quartz 已经配置了 `.gitignore`，会自动忽略：

- `.obsidian/` - Obsidian 配置文件夹
- `node_modules/` - Node.js 依赖
- `public/` - 构建输出

你可以放心使用 Obsidian 的所有功能。

### 3. 只编辑 content 文件夹

建议只在 `content/` 文件夹中创建和编辑笔记，不要修改其他文件（如 `quartz/`、`quartz.config.ts` 等），除非你知道自己在做什么。

## 🔧 故障排除

### 问题 1: 插件提示 "Not a git repository"

**解决方案**：
- 确保在 Obsidian 中打开的是 `d:\fuckwebot` 文件夹
- 检查该文件夹中是否有 `.git` 子文件夹

### 问题 2: 推送失败 "Authentication failed"

**解决方案**:

- 检查 Git 凭据是否正确
- 在命令行中手动执行 `git push` 测试
- 可能需要配置 Git 凭据管理器

### 问题 3: 网站没有更新

**解决方案**:

- 检查 Vercel 部署日志，看是否有构建错误
- 确认 GitHub 上的代码已经更新
- 等待 2-3 分钟，Vercel 部署需要时间

## ✨ 总结

使用 Obsidian Git 插件后，你的工作流程变得非常简单：

1. **在 Obsidian 中写作** - 专注于内容创作
2. **自动同步** - 插件自动提交和推送
3. **自动部署** - Vercel 自动更新网站
4. **完全自动化** - 无需手动操作 Git 命令

享受你的自动化知识库吧！🚀

---

*如有问题，请参考 Obsidian Git 插件文档或 Quartz 官方文档。*
