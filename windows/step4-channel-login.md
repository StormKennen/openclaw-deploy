# 🤖 步骤 4：登录机器人

> Windows 系统聊天渠道配置教程

**难度**: ⭐⭐ | **预计时间**: 20 分钟

---

## 📋 前置要求

- ✅ OpenClaw 已安装
- ✅ AI 模型已配置
- ✅ 已选择聊天渠道 (飞书/Telegram/企业微信等)

---

## 🎯 渠道选择建议

| 渠道 | 难度 | 适合人群 | 审核时间 | 推荐度 |
|------|------|----------|----------|--------|
| **飞书** | ⭐⭐ | 个人/企业 | 即时 | ⭐⭐⭐⭐⭐ |
| **Telegram** | ⭐ | 个人 (需科学上网) | 无需审核 | ⭐⭐⭐⭐⭐ |
| **企业微信** | ⭐⭐ | 企业用户 | 1-3 天 | ⭐⭐⭐⭐ |
| **钉钉** | ⭐⭐⭐ | 企业用户 | 1-3 天 | ⭐⭐⭐⭐ |

**详细对比**: [查看渠道配置](../channels/README.md)

---

## 🚀 登录步骤

### 方式 1: 飞书机器人 (推荐国内用户)

#### 步骤 1: 创建飞书应用

1. 访问 [飞书开放平台](https://open.feishu.cn/)
2. 登录飞书账号
3. 点击 **企业应用** → **创建应用**
4. 选择 **自建应用**
5. 填写应用信息：
   - 应用名称：OpenClaw Assistant
   - 应用图标：可选
   - 应用描述：个人 AI 助手
6. 点击 **创建**

#### 步骤 2: 配置权限

1. 点击左侧 **权限管理**
2. 点击 **申请权限**
3. 搜索并添加：
   - `im:message` (发送消息)
   - `im:message.p2p` (读取消息)
   - `im:chat` (群组机器人)
4. 点击 **提交申请**

#### 步骤 3: 获取凭证

1. 点击左侧 **凭证与基础信息**
2. 记录：
   - **App ID**: `cli_xxxxxxxxxxxxxxxx`
   - **App Secret**: 加密字符串

#### 步骤 4: 在 OpenClaw 中登录

打开 **PowerShell**，输入：

```powershell
openclaw channels login feishu
```

按提示输入：
- App ID
- App Secret

```
请输入飞书 App ID:
> cli_xxxxxxxxxxxxxxxx

请输入飞书 App Secret:
> (粘贴 Secret，不显示)
```

#### 步骤 5: 添加机器人到聊天

1. 在飞书中搜索你的应用名称
2. 点击应用，开始聊天

#### 步骤 6: 测试

发送消息：`你好`

机器人应该回复！

---

### 方式 2: Telegram 机器人 (最简单)

#### 步骤 1: 创建机器人

1. 在 Telegram 中搜索 **@BotFather**
2. 发送 `/newbot`
3. 输入机器人名称：OpenClaw Assistant
4. 输入机器人用户名：OpenClawBot (必须以 bot 结尾)
5. BotFather 返回 Token

#### 步骤 2: 获取 Chat ID

1. 搜索 **@userinfobot**
2. 发送 `/start`
3. 获取 Chat ID

或访问：
```
https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates
```

#### 步骤 3: 在 OpenClaw 中登录

```powershell
openclaw channels login telegram
```

按提示输入：
- Token
- Chat ID

#### 步骤 4: 测试

在 Telegram 中给机器人发消息测试

---

### 方式 3: 企业微信机器人

#### 步骤 1: 创建应用

1. 访问 [企业微信管理后台](https://work.weixin.qq.com/)
2. 点击 **应用管理** → **自建**
3. 创建应用

#### 步骤 2: 获取凭证

1. 查看 **AgentId** 和 **Secret**
2. 记录企业 ID

#### 步骤 3: 在 OpenClaw 中登录

```powershell
openclaw channels login wechat-work
```

按提示输入凭证

---

### 方式 4: 钉钉机器人

#### 步骤 1: 创建应用

1. 访问 [钉钉开放平台](https://open.dingtalk.com/)
2. 创建企业内部开发应用

#### 步骤 2: 获取凭证

1. 查看 **AppKey** 和 **AppSecret**

#### 步骤 3: 在 OpenClaw 中登录

```powershell
openclaw channels login dingtalk
```

---

## ⚙️ 查看和管理渠道

### 查看已登录渠道

```powershell
openclaw channels list
```

输出示例：
```
已登录渠道:
  ✅ 飞书 (OpenClaw Assistant)
  ✅ Telegram (@OpenClawBot)
```

---

### 退出渠道

```powershell
openclaw channels logout feishu
```

---

### 测试渠道

```powershell
openclaw channels test feishu
```

---

## 🆘 常见问题

### Q1: 飞书机器人不回复？

**可能原因**:
1. 权限未审批
2. 机器人未添加到聊天
3. Gateway 未启动

**解决方案**:
```powershell
# 检查 Gateway 状态
openclaw gateway status

# 查看日志
openclaw logs

# 确认权限已审批
# 访问 https://open.feishu.cn/
```

---

### Q2: Telegram 无法访问？

**问题**: 国内无法访问 Telegram

**解决方案**:
- 使用科学上网工具
- 或改用飞书机器人

---

### Q3: 凭证无效？

**错误信息**:
```
Error: Invalid credentials
```

**解决方案**:
1. 检查 App ID/Secret 是否正确
2. 确认应用已发布
3. 重新创建凭证

---

### Q4: 如何添加机器人到群聊？

**飞书**:
1. 打开群聊
2. 点击右上角 **...**
3. 点击 **添加成员**
4. 搜索机器人名称
5. 添加

**Telegram**:
1. 打开群聊
2. 点击群名称
3. 点击 **添加成员**
4. 搜索机器人
5. 添加

---

## 📊 配置检查清单

- [ ] 已选择聊天渠道
- [ ] 已创建应用/机器人
- [ ] 已获取凭证 (App ID/Secret 或 Token)
- [ ] 已在 OpenClaw 中登录
- [ ] 已添加机器人到聊天
- [ ] 测试消息成功

---

## 🎯 下一步

登录完成后，启动网关：

```powershell
# 启动 Gateway
openclaw gateway --port 18789

# 打开浏览器访问
# http://127.0.0.1:18789/
```

---

## 📚 详细教程

- [飞书完整配置](../channels/feishu.md)
- [Telegram 配置](../channels/telegram.md)
- [企业微信配置](../channels/wechat-work.md)
- [钉钉配置](../channels/dingtalk.md)

---

## 📞 获取帮助

- [渠道配置指南](../channels/README.md)
- [常见问题 FAQ](../../docs/FAQ.md)
- [Discord 社区](https://discord.com/invite/clawd)

---

[上一步：配置 AI 模型](./step3-model-config.md) | [返回 Windows 教程首页](./README.md) | [下一步：启动网关 →](#下一步启动网关)
