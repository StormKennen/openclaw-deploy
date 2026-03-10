# 🤖 步骤 4：登录机器人

> macOS 系统聊天渠道配置

**难度**: ⭐⭐ | **预计时间**: 20 分钟

---

## 🎯 渠道选择

| 渠道 | 难度 | 推荐度 |
|------|------|--------|
| 飞书 | ⭐⭐ | ⭐⭐⭐⭐⭐ |
| Telegram | ⭐ | ⭐⭐⭐⭐⭐ |
| 企业微信 | ⭐⭐ | ⭐⭐⭐⭐ |
| 钉钉 | ⭐⭐⭐ | ⭐⭐⭐⭐ |

---

## 🚀 登录步骤

### 飞书

```bash
# 1. 创建飞书应用
# 访问 https://open.feishu.cn/

# 2. 在 OpenClaw 中登录
openclaw channels login feishu

# 3. 输入 App ID 和 Secret
```

### Telegram

```bash
# 1. 联系 @BotFather 创建机器人

# 2. 在 OpenClaw 中登录
openclaw channels login telegram

# 3. 输入 Token 和 Chat ID
```

---

## 📚 详细教程

- [飞书配置](../channels/feishu.md)
- [Telegram 配置](../channels/telegram.md)

---

[上一步：配置 AI 模型](./step3-model-config.md) | [返回 macOS 教程首页](./README.md) | [下一步：启动网关 →](#下一步启动网关)
