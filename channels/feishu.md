# 📱 飞书机器人配置指南

> 个人/企业最常用的 AI 助理接入方式

**难度**: ⭐⭐ | **预计时间**: 20 分钟

---

## 📋 准备工作

### 必需条件
- [ ] 飞书账号 (个人/企业均可)
- [ ] 手机号 (用于注册)
- [ ] 电脑 (配置过程需要浏览器)

### 注册飞书
1. 访问 [飞书官网](https://www.feishu.cn/)
2. 点击 **免费下载**
3. 使用手机号注册
4. 下载并安装飞书客户端

---

## 🚀 配置步骤

### 步骤 1: 创建飞书应用

1. 访问 [飞书开放平台](https://open.feishu.cn/)
2. 点击右上角 **登录**，使用飞书账号登录

![飞书开放平台登录](https://open.feishu.cn/assets/login.png)

3. 进入 **企业应用** → **创建应用**
4. 选择 **自建应用**

![创建应用](https://open.feishu.cn/assets/create-app.png)

5. 填写应用信息：
   - **应用名称**: OpenClaw Assistant (或你喜欢的名字)
   - **应用图标**: 可选 (可上传 OpenClaw logo)
   - **应用描述**: 个人 AI 助手
6. 点击 **创建**

---

### 步骤 2: 配置应用权限

1. 进入应用管理页面
2. 点击左侧 **权限管理**

![权限管理](https://open.feishu.cn/assets/permissions.png)

3. 点击 **申请权限**

4. 搜索并添加以下权限：

| 权限名称 | 权限标识 | 用途 |
|----------|----------|------|
| 发送消息 | `im:message` | 发送消息给用户 |
| 读取消息 | `im:message.p2p` | 接收用户消息 |
| 群组机器人 | `im:chat` | 加入群聊 |
| 文档读写 | `drive:doc` | 读写飞书文档 (可选) |
| 云空间管理 | `drive:file` | 管理云空间文件 (可选) |

![申请权限](https://open.feishu.cn/assets/request-permissions.png)

5. 点击 **提交申请**

> ⚠️ **注意**: 个人账号通常自动审批，企业账号可能需要管理员审批

---

### 步骤 3: 获取凭证

1. 在应用管理页面，点击 **凭证与基础信息**

![凭证信息](https://open.feishu.cn/assets/credentials.png)

2. 记录以下信息：
   - **App ID**: `cli_xxxxxxxxxxxxxxxx`
   - **App Secret**: 一串加密字符串

> ⚠️ **重要**: 妥善保管 App Secret，不要泄露！

3. 开启 **机器人** 功能
   - 点击左侧 **机器人**
   - 开启机器人开关
   - 设置机器人昵称和头像

---

### 步骤 4: 配置事件订阅 (可选)

如果需要实时接收消息：

1. 点击左侧 **事件订阅**
2. 点击 **开通配置**

![事件订阅](https://open.feishu.cn/assets/event-subscription.png)

3. 填写 **请求地址** (需要公网可访问的 URL)
   - 本地测试可用 [ngrok](https://ngrok.com/) 或 [natapp](https://natapp.cn/)
   - 生产环境使用自己的服务器

4. 选择订阅的事件：
   - `im.message.receive_v1` - 接收消息

5. 保存配置

---

### 步骤 5: 将机器人添加到聊天

#### 方式 1: 个人聊天

1. 在飞书客户端，搜索你的应用名称
2. 点击应用，开始聊天

#### 方式 2: 群聊

1. 在飞书客户端，创建一个群聊 (或选择现有群)
2. 点击右上角 **...** → **添加成员**

![添加机器人](https://open.feishu.cn/assets/add-bot.png)

3. 搜索你的应用名称
4. 添加机器人到聊天

---

## 🔧 OpenClaw 配置

### 方式 1: 使用配置向导

```bash
# 运行配置向导
openclaw onboard

# 选择飞书渠道
# 按提示输入 App ID 和 App Secret
```

### 方式 2: 手动配置

编辑配置文件 `~/.openclaw/config.json`:

```json
{
  "channels": {
    "feishu": {
      "appId": "cli_xxxxxxxxxxxxxxxx",
      "appSecret": "你的 App Secret",
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

1. 在飞书中给机器人发送消息
2. 机器人应该回复 (如果配置了 AI 模型)

### 查看日志

```bash
# 查看实时日志
openclaw logs

# 查看错误日志
openclaw logs --level error
```

### 常见问题排查

| 问题 | 可能原因 | 解决方案 |
|------|----------|----------|
| 机器人不回复 | 权限未审批 | 等待审批或联系管理员 |
| 认证失败 | App Secret 错误 | 检查是否复制完整 |
| 无法添加机器人 | 应用未发布 | 点击 **版本管理** → **发布** |

---

## 🎯 高级配置

### 自定义机器人形象

1. 在应用管理页面，点击 **基础信息**
2. 上传机器人头像
3. 修改机器人昵称

### 配置机器人欢迎语

1. 点击左侧 **机器人**
2. 编辑 **欢迎语**
3. 设置用户首次打开时的欢迎消息

### 添加快捷菜单

1. 点击左侧 **机器人**
2. 配置 **快捷菜单**
3. 添加常用命令按钮

---

## 📊 用量统计

### 查看消息量

1. 登录 [飞书开放平台](https://open.feishu.cn/)
2. 进入应用管理
3. 点击 **数据统计**

### 设置用量告警

1. 点击 **告警配置**
2. 设置每日消息量阈值
3. 配置通知方式 (邮件/短信)

---

## 🆘 常见问题

### Q: 个人账号可以创建应用吗？

**A**: 可以！个人账号可以创建自建应用，部分权限可能需要企业账号。

### Q: 审批需要多久？

**A**: 
- 个人账号：通常自动审批，即时生效
- 企业账号：1-3 个工作日 (取决于管理员)

### Q: 机器人可以在多个群使用吗？

**A**: 可以！添加机器人到多个群即可。

### Q: 消息有数量限制吗？

**A**: 
- 免费版：1000 条/分钟
- 企业版：联系销售提升限额

### Q: 如何删除机器人？

**A**: 
1. 在飞书开放平台删除应用
2. 或在聊天中移除机器人

---

## 📚 参考资源

- [飞书开放平台文档](https://open.feishu.cn/document/home)
- [飞书机器人开发指南](https://open.feishu.cn/document/ukTMukTMukTM/ucDOzYjLwgjMx4jMzYjN)
- [OpenClaw 飞书插件](https://github.com/openclaw/openclaw/tree/main/extensions/feishu)

---

[返回主页](../README.md) | [上一篇：模型配置](../models/README.md) | [下一篇：企业微信](./wechat-work.md)
