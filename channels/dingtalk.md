# 📌 钉钉机器人配置指南

> 企业用户备选方案，阿里生态集成

**难度**: ⭐⭐⭐ | **预计时间**: 30 分钟

---

## 📋 准备工作

### 必需条件
- [ ] 钉钉账号 (需要企业管理员权限)
- [ ] 已认证的钉钉组织
- [ ] 电脑 (配置过程需要浏览器)

---

## 🚀 配置步骤

### 步骤 1: 创建钉钉应用

1. 访问 [钉钉开放平台](https://open.dingtalk.com/)
2. 登录钉钉管理后台
3. 点击 **应用开发** → **企业内部开发**

![创建应用](https://open.dingtalk.com/assets/create-app.png)

4. 创建应用：
   - **应用名称**: OpenClaw Assistant
   - **应用图标**: 上传 Logo
   - **应用类型**: H5 微应用

---

### 步骤 2: 获取凭证

1. 进入应用详情页
2. 点击 **凭证与基础信息**

![凭证信息](https://open.dingtalk.com/assets/credentials.png)

3. 记录以下信息：
   - **AppKey**: 应用 Key
   - **AppSecret**: 应用 Secret

---

### 步骤 3: 配置机器人

1. 点击 **机器人** 功能
2. 开启机器人
3. 配置机器人昵称和头像

---

### 步骤 4: 添加权限

1. 点击 **权限管理**
2. 添加以下权限：
   - 发送工作通知
   - 接收消息
   - 群机器人

---

## 🔧 OpenClaw 配置

### 配置文件

编辑 `~/.openclaw/config.json`:

```json
{
  "channels": {
    "dingtalk": {
      "appKey": "你的 AppKey",
      "appSecret": "你的 AppSecret",
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

## 🆘 常见问题

### Q: 和飞书比怎么样？

**A**: 功能类似，但钉钉配置稍复杂，飞书更友好。

### Q: 审核需要多久？

**A**: 通常 1-3 个工作日。

---

[返回主页](../README.md) | [上一篇：企业微信](./wechat-work.md) | [下一篇：Telegram](./telegram.md)
