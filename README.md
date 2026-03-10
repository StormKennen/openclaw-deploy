# 🦞 OpenClaw 部署指南

> 从零开始，7 天掌握你的 AI 私人助理 - 中文保姆级教程

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-2026.3.8-green.svg)](https://github.com/openclaw/openclaw)
[![中文教程](https://img.shields.io/badge/教程 - 中文-red.svg)](README.md)

---

## 📖 仓库定位

**本仓库提供：**
- 🖥️ **Windows/Mac** 双平台保姆级部署教程
- 💰 **便宜 API 模型** 注册指南（阿里云、智谱、DeepSeek 等）
- 🤖 **国内机器人** 整合（飞书、企业微信、钉钉）
- 📱 **平台注册** 完整流程（账号申请、权限配置）

**适合人群：**
- 🌱 零基础新手 - 手把手教学，图文并茂
- 💼 开发者 - 快速搭建个人 AI 助理
- 🏢 企业用户 - 集成飞书/企业微信/钉钉

---

## 🚀 5 分钟快速开始

### Windows 用户
```powershell
# 1. 安装 Node.js (从 https://nodejs.org/)
# 2. 安装 OpenClaw
npm install -g openclaw@latest

# 3. 运行向导
openclaw onboard --install-daemon

# 4. 登录机器人
openclaw channels login

# 5. 启动网关
openclaw gateway --port 18789
```

### macOS 用户
```bash
# 1. 安装 Node.js (使用 Homebrew)
brew install node@22

# 2. 安装 OpenClaw
npm install -g openclaw@latest

# 3. 运行向导
openclaw onboard --install-daemon

# 4. 登录机器人
openclaw channels login

# 5. 启动网关
openclaw gateway --port 18789
```

---

## 📚 完整教程

### Windows 部署
| 步骤 | 文档 | 预计时间 |
|------|------|----------|
| 1 | [安装 Node.js](./windows/step1-install-nodejs.md) | 10 分钟 |
| 2 | [安装 OpenClaw](./windows/step2-install-openclaw.md) | 5 分钟 |
| 3 | [配置 AI 模型](./windows/step3-model-config.md) | 15 分钟 |
| 4 | [登录机器人](./windows/step4-channel-login.md) | 20 分钟 |

[查看 Windows 完整教程 →](./windows/README.md)

### macOS 部署
| 步骤 | 文档 | 预计时间 |
|------|------|----------|
| 1 | [安装 Node.js](./macos/step1-install-nodejs.md) | 10 分钟 |
| 2 | [安装 OpenClaw](./macos/step2-install-openclaw.md) | 5 分钟 |
| 3 | [配置 AI 模型](./macos/step3-model-config.md) | 15 分钟 |
| 4 | [登录机器人](./macos/step4-channel-login.md) | 20 分钟 |

[查看 macOS 完整教程 →](./macos/README.md)

---

## 💰 便宜模型推荐

| 模型 | 提供商 | 价格 (每 1M tokens) | 推荐度 | 文档 |
|------|--------|---------------------|--------|------|
| **GLM-4-Flash** | 智谱 AI | ¥0.1 (统一) | ⭐⭐⭐⭐⭐ | [查看](./models/zhipu-ai.md) |
| **Qwen-Plus** | 阿里云 | ¥2 (输入) / ¥6 (输出) | ⭐⭐⭐⭐⭐ | [查看](./models/aliyun-bailian.md) |
| **DeepSeek-V2** | DeepSeek | ¥1 (输入) / ¥2 (输出) | ⭐⭐⭐⭐ | [查看](./models/deepseek.md) |

> 💡 **新手推荐**: 智谱 AI GLM-4-Flash (最便宜，¥0.1/1M tokens)

[查看所有模型对比 →](./models/README.md)

---

## 🤖 机器人渠道

| 渠道 | 难度 | 适合场景 | 审核时间 | 文档 |
|------|------|----------|----------|------|
| **Telegram** | ⭐ | 个人 | 无需审核 | [查看](./channels/telegram.md) |
| **飞书** | ⭐⭐ | 个人/企业 | 即时 | [查看](./channels/feishu.md) |
| **企业微信** | ⭐⭐ | 企业 | 1-3 天 | [查看](./channels/wechat-work.md) |
| **钉钉** | ⭐⭐⭐ | 企业 | 1-3 天 | [查看](./channels/dingtalk.md) |

> 💡 **新手推荐**: 
> - 个人用户：Telegram (最简单) 或 飞书 (国内可用)
> - 企业用户：飞书 (审核快，体验好)

[查看所有渠道配置 →](./channels/README.md)

---

## 📅 7 天学习路径

| 天数 | 主题 | 目标 | 文档 |
|------|------|------|------|
| **Day 1** | 认识 OpenClaw | 了解功能和架构 | - |
| **Day 2** | 环境准备 | 安装 Node.js | [Windows](./windows/README.md) / [macOS](./macos/README.md) |
| **Day 3** | 安装 OpenClaw | 完成安装配置 | [安装教程](./windows/step2-install-openclaw.md) |
| **Day 4** | 模型配置 | 注册 API 获取密钥 | [模型配置](./models/README.md) |
| **Day 5** | 机器人配置 | 飞书/Telegram 接入 | [渠道配置](./channels/README.md) |
| **Day 6** | 技能开发 | 编写第一个技能 | - |
| **Day 7** | 实战应用 | 集成到工作流 | - |

---

## 🆘 常见问题

### 安装问题

**Q: npm 安装失败？**
```bash
# 清除缓存重试
npm cache clean --force
npm install -g openclaw@latest

# 使用国内镜像
npm config set registry https://registry.npmmirror.com
```

**Q: 权限不足？**
- Windows: 以管理员身份运行 PowerShell
- macOS: 配置 npm 全局目录权限

### 模型配置

**Q: 哪个模型最便宜？**
- 智谱 AI GLM-4-Flash: ¥0.1/1M tokens
- 每天正常使用，每月不到 ¥1！

**Q: API Key 无效？**
- 检查密钥是否复制完整
- 确认账户完成实名认证
- 确认账户有余额

### 机器人登录

**Q: 飞书机器人不回复？**
- 检查应用权限是否审批
- 确认机器人已添加到聊天
- 查看 Gateway 是否正常运行

[查看更多常见问题 →](./docs/FAQ.md)

---

## 🛠️ 辅助工具

### 环境检查
```bash
# 检查 Node.js 版本
node --version  # 需要 22+

# 检查 npm
npm --version

# 检查 OpenClaw
openclaw --version
```

### 查看日志
```bash
# 实时日志
openclaw logs

# 错误日志
openclaw logs --level error
```

### 配置备份
```bash
# 备份配置文件
cp ~/.openclaw/config.json ~/.openclaw/config.json.backup
```

---

## 📚 参考资源

### 官方资源
- [OpenClaw 官方文档](https://docs.openclaw.ai/)
- [OpenClaw GitHub](https://github.com/openclaw/openclaw)
- [OpenClaw Discord](https://discord.com/invite/clawd)

### 模型提供商
- [智谱 AI](https://open.bigmodel.cn/) - 最便宜
- [阿里云百炼](https://bailian.console.aliyun.com/) - 企业级
- [DeepSeek](https://www.deepseek.com/) - 代码能力强

### 机器人平台
- [飞书开放平台](https://open.feishu.cn/) - 推荐
- [Telegram Bot API](https://core.telegram.org/bots/api) - 最简单
- [企业微信](https://work.weixin.qq.com/) - 企业用户
- [钉钉开放平台](https://open.dingtalk.com/) - 阿里生态

---

## 🤝 贡献指南

欢迎贡献！本仓库接受以下类型的贡献：

- 📝 教程改进
- 🐛 问题修复
- 💡 新功能建议
- 🌐 翻译改进

### 贡献方式
1. Fork 本仓库
2. 创建分支 `git checkout -b feature/xxx`
3. 提交更改 `git commit -m 'Add some feature'`
4. 推送到分支 `git push origin feature/xxx`
5. 创建 Pull Request

---

## 📄 许可证

[MIT License](./LICENSE)

---

<div align="center">

**Made with 🦞 by OpenClaw Community**

[返回顶部](#-openclaw-部署指南)

</div>
