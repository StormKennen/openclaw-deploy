# 🤖 企业微信机器人配置指南

> 企业用户首选，与办公场景深度集成

**难度**: ⭐⭐ | **预计时间**: 25 分钟

---

## 📋 准备工作

### 必需条件
- [ ] 企业微信账号 (需要企业管理员权限)
- [ ] 已认证的企业微信主体
- [ ] 电脑 (配置过程需要浏览器)

### 注册企业微信
1. 访问 [企业微信官网](https://work.weixin.qq.com/)
2. 点击 **立即注册**
3. 填写企业信息
4. 等待审核 (通常 1-3 个工作日)

> ⚠️ **注意**: 个人用户无法使用企业微信，需要使用飞书或 Telegram

---

## 🚀 配置步骤

### 步骤 1: 创建自建应用

1. 登录 [企业微信管理后台](https://work.weixin.qq.com/)
2. 点击 **应用管理** → **应用** → **自建**

![创建应用](https://work.weixin.qq.com/assets/create-app.png)

3. 填写应用信息：
   - **应用名称**: OpenClaw Assistant
   - **应用图标**: 上传 Logo
   - **可见范围**: 选择全员或指定部门
4. 点击 **创建**

---

### 步骤 2: 配置应用

1. 进入应用详情页
2. 点击 **AgentId** 和 **Secret** 旁边的显示按钮

![凭证信息](https://work.weixin.qq.com/assets/credentials.png)

3. 记录以下信息：
   - **AgentId**: 数字 ID
   - **Secret**: 加密字符串

> ⚠️ **重要**: 妥善保管 Secret，不要泄露！

---

### 步骤 3: 配置接收消息

1. 点击 **接收消息** 设置

![接收消息](https://work.weixin.qq.com/assets/message-settings.png)

2. 配置 **API 接收消息**:
   - **URL**: 你的服务器地址 (需要公网可访问)
   - **Token**: 自定义 Token
   - **EncodingAESKey**: 系统生成或自定义

3. 保存配置

> ⚠️ **注意**: 本地测试需要使用内网穿透工具 (ngrok/natapp)

---

### 步骤 4: 配置企业可信 IP

1. 点击 **企业可信 IP**
2. 添加你的服务器 IP 地址
3. 保存配置

---

## 🔧 OpenClaw 配置

### 配置文件

编辑 `~/.openclaw/config.json`:

```json
{
  "channels": {
    "wechat-work": {
      "corpId": "你的企业 ID",
      "agentId": 1000001,
      "secret": "你的 Secret",
      "token": "你的 Token",
      "encodingAesKey": "你的 EncodingAESKey",
      "enabled": true
    }
  }
}
```

### 启动 Gateway

```bash
# 启动网关
openclaw gateway --port 18789

# 查看状态
openclaw gateway status
```

---

## ✅ 验证与测试

### 测试消息

1. 在企业微信中找到应用
2. 发送消息测试
3. 查看是否回复

### 查看日志

```bash
# 查看实时日志
openclaw logs
```

---

## 🆘 常见问题

### Q: 个人可以使用吗？

**A**: 不可以，企业微信仅限企业用户。个人用户推荐使用飞书。

### Q: 审核需要多久？

**A**: 企业认证通常 1-3 个工作日。

### Q: 消息有限制吗？

**A**: 企业认证后无限制。

---

[返回主页](../README.md) | [上一篇：飞书](./feishu.md) | [下一篇：钉钉](./dingtalk.md)
