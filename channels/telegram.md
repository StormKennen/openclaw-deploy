# ✈️ Telegram 机器人配置指南

> 个人用户首选，配置最简单

**难度**: ⭐ | **预计时间**: 10 分钟

---

## 📋 准备工作

### 必需条件
- [ ] Telegram 账号 (需要科学上网)
- [ ] 手机或电脑 (安装 Telegram 客户端)

### 注册 Telegram
1. 下载 Telegram 客户端
2. 使用手机号注册
3. 完成验证

---

## 🚀 配置步骤

### 步骤 1: 联系 BotFather

1. 在 Telegram 中搜索 **@BotFather**
2. 点击 **Start** 开始对话

![BotFather](https://telegram.org/assets/botfather.png)

---

### 步骤 2: 创建机器人

1. 发送命令 `/newbot`
2. 按提示输入：
   - **机器人名称**: OpenClaw Assistant
   - **机器人用户名**: OpenClawBot (必须以 bot 结尾)

![创建机器人](https://telegram.org/assets/create-bot.png)

3. 创建成功后，BotFather 会发送 **Token**

> ⚠️ **重要**: 妥善保管 Token，不要泄露！

---

### 步骤 3: 获取 Chat ID

1. 在 Telegram 中搜索 **@userinfobot**
2. 点击 **Start**
3. 机器人会返回你的 Chat ID

或者使用浏览器访问：
```
https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates
```

---

## 🔧 OpenClaw 配置

### 配置文件

编辑 `~/.openclaw/config.json`:

```json
{
  "channels": {
    "telegram": {
      "token": "你的 Bot Token",
      "chatId": "你的 Chat ID",
      "enabled": true
    }
  }
}
```

### 启动 Gateway

```bash
openclaw gateway --port 18789
```

---

## ✅ 验证与测试

### 测试消息

1. 在 Telegram 中给你的机器人发消息
2. 机器人应该回复

---

## 🆘 常见问题

### Q: 无法访问 Telegram？

**A**: 需要使用科学上网工具。

### Q: Token 泄露了怎么办？

**A**: 
1. 立即联系 @BotFather
2. 发送 `/revoke` 撤销旧 Token
3. 重新获取新 Token

### Q: 机器人不回复？

**A**: 
- 检查 Token 是否正确
- 确认 Gateway 已启动
- 查看日志 `openclaw logs`

---

## 🎯 高级配置

### 设置机器人头像

1. 联系 @BotFather
2. 发送 `/setuserpic`
3. 按提示上传头像

### 配置机器人描述

1. 联系 @BotFather
2. 发送 `/setdescription`
3. 输入机器人描述

---

[返回主页](../README.md) | [上一篇：钉钉](./dingtalk.md)
