# 🤖 机器人渠道配置

> 飞书、企业微信、钉钉、Telegram 完整配置指南

---

## 📊 渠道对比

| 渠道 | 难度 | 适合场景 | 审核时间 | 文档 |
|------|------|----------|----------|------|
| **飞书** | ⭐⭐ | 个人/企业 | 即时 | [查看](./feishu.md) |
| **Telegram** | ⭐ | 个人 | 无需审核 | [查看](./telegram.md) |
| **企业微信** | ⭐⭐ | 企业 | 1-3 天 | [查看](./wechat-work.md) |
| **钉钉** | ⭐⭐⭐ | 企业 | 1-3 天 | [查看](./dingtalk.md) |

---

## 🎯 选择建议

### 个人用户
- **首选**: Telegram (最简单，10 分钟搞定)
- **备选**: 飞书 (国内可用，功能完善)

### 企业用户
- **首选**: 飞书 (审核快，体验好)
- **备选**: 企业微信 (办公场景集成)
- **备选**: 钉钉 (阿里生态)

---

## 📚 配置教程

### [飞书机器人](./feishu.md) ⭐⭐

**适合**: 个人/企业用户

**步骤概览**:
1. 注册飞书账号
2. 创建飞书应用
3. 配置权限
4. 获取 App ID 和 Secret
5. OpenClaw 配置

**预计时间**: 20 分钟

---

### [Telegram 机器人](./telegram.md) ⭐

**适合**: 个人用户 (需科学上网)

**步骤概览**:
1. 注册 Telegram
2. 联系 @BotFather
3. 创建机器人
4. 获取 Token
5. OpenClaw 配置

**预计时间**: 10 分钟

---

### [企业微信机器人](./wechat-work.md) ⭐⭐

**适合**: 企业用户

**步骤概览**:
1. 注册企业微信
2. 创建自建应用
3. 获取 AgentId 和 Secret
4. 配置接收消息
5. OpenClaw 配置

**预计时间**: 25 分钟

---

### [钉钉机器人](./dingtalk.md) ⭐⭐⭐

**适合**: 企业用户 (阿里生态)

**步骤概览**:
1. 注册钉钉组织
2. 创建钉钉应用
3. 获取 AppKey 和 Secret
4. 配置机器人
5. OpenClaw 配置

**预计时间**: 30 分钟

---

## 🔧 通用配置

### OpenClaw 配置文件

编辑 `~/.openclaw/config.json`:

```json
{
  "channels": {
    "feishu": {
      "appId": "cli_xxx",
      "appSecret": "xxx",
      "enabled": true
    },
    "telegram": {
      "token": "xxx:xxx",
      "chatId": "123456",
      "enabled": true
    },
    "wechat-work": {
      "corpId": "xxx",
      "agentId": 1000001,
      "secret": "xxx",
      "enabled": true
    },
    "dingtalk": {
      "appKey": "xxx",
      "appSecret": "xxx",
      "enabled": true
    }
  }
}
```

### 启动网关

```bash
# 启动 Gateway
openclaw gateway --port 18789

# 查看状态
openclaw gateway status

# 查看日志
openclaw logs
```

---

## ✅ 验证测试

### 测试步骤

1. **发送消息**: 在机器人聊天窗口发送测试消息
2. **查看回复**: 确认机器人是否回复
3. **检查日志**: `openclaw logs` 查看是否有错误

### 常见问题

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 不回复 | 权限未审批 | 等待审批 |
| 认证失败 | Key/Secret 错误 | 检查配置 |
| 无法添加 | 应用未发布 | 点击发布 |

---

## 📚 参考资源

- [飞书开放平台](https://open.feishu.cn/)
- [Telegram Bot API](https://core.telegram.org/bots/api)
- [企业微信文档](https://work.weixin.qq.com/api/doc)
- [钉钉开放平台](https://open.dingtalk.com/)

---

[返回主页](../README.md)
