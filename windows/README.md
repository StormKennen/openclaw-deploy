# 🖥️ Windows 部署指南

> Windows 10/11 系统 OpenClaw 完整部署教程

---

## 📋 系统要求

| 要求 | 说明 |
|------|------|
| **操作系统** | Windows 10/11 (64 位) |
| **内存** | 至少 4GB (推荐 8GB+) |
| **磁盘** | 至少 2GB 可用空间 |
| **网络** | 稳定的互联网连接 |

---

## 🚀 快速开始

### 步骤 1: 安装 Node.js

1. 访问 [Node.js 官网](https://nodejs.org/)
2. 下载 **LTS 版本** (长期支持版)
3. 双击安装包，按提示安装
4. 验证安装：

```powershell
# 打开 PowerShell
node --version
npm --version
```

**详细教程**: [安装 Node.js](./step1-install-nodejs.md)

---

### 步骤 2: 安装 OpenClaw

```powershell
# 以管理员身份运行 PowerShell
npm install -g openclaw@latest

# 验证安装
openclaw --version
```

**详细教程**: [安装 OpenClaw](./step2-install-openclaw.md)

---

### 步骤 3: 配置 AI 模型

```powershell
# 运行配置向导
openclaw onboard

# 按提示选择模型提供商并输入 API Key
```

**详细教程**: [配置模型](./step3-model-config.md)

---

### 步骤 4: 登录机器人

```powershell
# 登录聊天渠道
openclaw channels login

# 按提示选择渠道 (飞书/Telegram/企业微信等)
```

**详细教程**: [登录机器人](./step4-channel-login.md)

---

### 步骤 5: 启动网关

```powershell
# 启动 Gateway
openclaw gateway --port 18789

# 打开浏览器访问
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

### Q: npm 安装失败？

**A**: 
```powershell
# 清除缓存
npm cache clean --force

# 使用镜像
npm config set registry https://registry.npmmirror.com

# 重新安装
npm install -g openclaw@latest
```

### Q: 权限不足？

**A**: 
- 右键 PowerShell → **以管理员身份运行**

### Q: 端口被占用？

**A**: 
```powershell
# 使用其他端口
openclaw gateway --port 18790
```

---

## 📚 参考资源

- [Node.js 官网](https://nodejs.org/)
- [OpenClaw 官方文档](https://docs.openclaw.ai/)
- [常见问题](../docs/FAQ.md)

---

[返回主页](../README.md) | [下一篇：macOS](../macos/README.md)
