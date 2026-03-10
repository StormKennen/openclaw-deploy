# 🦞 步骤 2：安装 OpenClaw

> macOS 系统 OpenClaw 安装教程

**难度**: ⭐⭐ | **预计时间**: 5 分钟

---

## 📋 前置要求

- ✅ 已安装 Node.js 22+
- ✅ 已配置 npm 镜像

---

## 🚀 安装步骤

### 步骤 1: 打开终端

按 `Cmd + Space`，输入 `Terminal`，回车

---

### 步骤 2: 安装 OpenClaw

```bash
npm install -g openclaw@latest
```

---

### 步骤 3: 验证安装

```bash
openclaw --version
```

---

### 步骤 4: 查看帮助

```bash
openclaw --help
```

---

## ⚙️ 修复权限问题

```bash
# 创建全局目录
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
```

---

## 🆘 常见问题

### Q: 权限错误？

```bash
# 使用 sudo
sudo npm install -g openclaw@latest

# 或修复权限 (推荐)
# 见上方修复权限步骤
```

---

## 📚 下一步

[配置 AI 模型 →](./step3-model-config.md)

---

[上一步：安装 Node.js](./step1-install-nodejs.md) | [返回 macOS 教程首页](./README.md) | [下一步：配置 AI 模型 →](./step3-model-config.md)
