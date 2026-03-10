# 🍎 macOS 部署指南

> macOS 系统 OpenClaw 完整部署教程

---

## 📋 系统要求

| 要求 | 说明 |
|------|------|
| **操作系统** | macOS 11+ (Big Sur 或更高) |
| **芯片** | Intel 或 Apple Silicon (M1/M2/M3) |
| **内存** | 至少 4GB (推荐 8GB+) |
| **磁盘** | 至少 2GB 可用空间 |

---

## 🚀 快速开始

### 步骤 1: 安装 Node.js

**方式 1: 使用官网安装包**

1. 访问 [Node.js 官网](https://nodejs.org/)
2. 下载 **LTS 版本**
3. 双击 `.pkg` 文件安装
4. 验证安装：

```bash
node --version
npm --version
```

**方式 2: 使用 Homebrew (推荐)**

```bash
# 安装 Homebrew (如果未安装)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 安装 Node.js
brew install node@22

# 验证
node --version
```

**详细教程**: [安装 Node.js](./step1-install-nodejs.md)

---

### 步骤 2: 安装 OpenClaw

```bash
# 安装 OpenClaw
npm install -g openclaw@latest

# 验证
openclaw --version
```

**详细教程**: [安装 OpenClaw](./step2-install-openclaw.md)

---

### 步骤 3: 配置 AI 模型

```bash
# 运行配置向导
openclaw onboard

# 按提示选择模型并输入 API Key
```

**详细教程**: [配置模型](./step3-model-config.md)

---

### 步骤 4: 登录机器人

```bash
# 登录聊天渠道
openclaw channels login

# 选择渠道 (飞书/Telegram 等)
```

**详细教程**: [登录机器人](./step4-channel-login.md)

---

### 步骤 5: 启动网关

```bash
# 启动 Gateway
openclaw gateway --port 18789

# 浏览器访问
# http://127.0.0.1:18789/
```

---

## 📁 完整教程目录

| 步骤 | 文档 | 预计时间 |
|------|------|----------|
| 1 | [安装 Node.js](./step1-install-nodejs.md) | 10 分钟 |
| 2 | [安装 OpenClaw](./step2-install-openclaw.md) | 5 分钟 |
| 3 | [配置 AI 模型](./step3-model-config.md) | 15 分钟 |
| 4 | [登录机器人](./step4-channel-login.md) | 20 分钟 |

---

## 🆘 常见问题

### Q: npm 权限错误？

**A**: 
```bash
# 修复 npm 权限
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc

# 重新安装
npm install -g openclaw@latest
```

### Q: 端口被占用？

**A**: 
```bash
# 使用其他端口
openclaw gateway --port 18790
```

### Q: 无法访问外网？

**A**: 
- 使用国内镜像：`npm config set registry https://registry.npmmirror.com`

---

## 📚 参考资源

- [Node.js 官网](https://nodejs.org/)
- [Homebrew](https://brew.sh/)
- [OpenClaw 官方文档](https://docs.openclaw.ai/)

---

[返回主页](../README.md) | [上一篇：Windows](../windows/README.md)
