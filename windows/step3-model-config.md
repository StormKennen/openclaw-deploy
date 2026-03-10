# 💰 步骤 3：配置 AI 模型

> Windows 系统模型配置详细教程

**难度**: ⭐⭐⭐ | **预计时间**: 15 分钟

---

## 📋 前置要求

- ✅ OpenClaw 已安装
- ✅ 已选择模型提供商 (智谱/阿里云/DeepSeek)
- ✅ 已注册对应平台账号

---

## 🎯 模型选择建议

### 新手推荐

| 模型 | 价格 | 特点 | 适合场景 |
|------|------|------|----------|
| **智谱 GLM-4-Flash** | ¥0.1/1M | 最便宜 | 日常对话、文档总结 |
| **阿里云 Qwen-Plus** | ¥2/1M | 稳定可靠 | 企业应用、复杂任务 |
| **DeepSeek-V2** | ¥1/1M | 代码能力强 | 编程助手、逻辑推理 |

**详细对比**: [查看模型价格](../models/README.md)

---

## 🚀 配置步骤

### 方式 1: 使用配置向导 (推荐)

#### 步骤 1: 运行配置向导

打开 **PowerShell**，输入：

```powershell
openclaw onboard
```

#### 步骤 2: 选择模型提供商

向导会显示可选模型：

```
选择模型提供商:
  1. 智谱 AI (最便宜，¥0.1/1M)
  2. 阿里云百炼 (企业级，稳定)
  3. DeepSeek (代码能力强)
  4. 其他...

请输入选项 (1-4): 
```

输入对应数字，如：`1`

#### 步骤 3: 输入 API Key

```
请输入 API Key:
> 
```

粘贴你从模型平台获取的 API Key

> ⚠️ **注意**: API Key 不会显示，直接粘贴即可

#### 步骤 4: 选择模型

```
选择模型:
  1. glm-4-flash (推荐)
  2. glm-4
  3. glm-3-turbo

请输入选项 (1-3): 
```

输入对应数字，推荐选择 `1`

#### 步骤 5: 测试连接

```
正在测试连接...
✅ 连接成功！
模型：glm-4-flash
余额：¥10.00
```

#### 步骤 6: 完成配置

```
✅ 配置完成！

配置文件：C:\Users\<用户名>\.openclaw\config.json

接下来:
  1. 配置聊天渠道：openclaw channels login
  2. 启动网关：openclaw gateway
```

---

### 方式 2: 手动配置

#### 步骤 1: 编辑配置文件

打开配置文件：

```powershell
notepad "$env:USERPROFILE\.openclaw\config.json"
```

#### 步骤 2: 添加模型配置

**智谱 AI 配置**:
```json
{
  "models": {
    "zhipu": {
      "apiKey": "你的 API_KEY",
      "modelId": "glm-4-flash",
      "enabled": true
    }
  }
}
```

**阿里云百炼配置**:
```json
{
  "models": {
    "bailian": {
      "apiKey": "sk-你的 API_KEY",
      "modelId": "qwen-plus",
      "enabled": true
    }
  }
}
```

**DeepSeek 配置**:
```json
{
  "models": {
    "deepseek": {
      "apiKey": "sk-你的 API_KEY",
      "modelId": "deepseek-chat",
      "enabled": true
    }
  }
}
```

#### 步骤 3: 保存文件

按 `Ctrl + S` 保存，关闭记事本

#### 步骤 4: 验证配置

```powershell
openclaw models test
```

---

## 🔑 获取 API Key

### 智谱 AI

1. 访问 [智谱 AI 开放平台](https://open.bigmodel.cn/)
2. 登录账号
3. 点击 **API Key 管理**
4. 点击 **添加 API Key**
5. 输入名称 (如：OpenClaw)
6. 复制 API Key

**详细教程**: [查看](../models/zhipu-ai.md)

---

### 阿里云百炼

1. 访问 [阿里云百炼](https://bailian.console.aliyun.com/)
2. 登录阿里云账号
3. 点击 **API-KEY 管理**
4. 点击 **创建新的 API-KEY**
5. 输入名称
6. 复制 API Key

**详细教程**: [查看](../models/aliyun-bailian.md)

---

### DeepSeek

1. 访问 [DeepSeek 开放平台](https://platform.deepseek.com/)
2. 登录账号
3. 点击 **API Keys**
4. 点击 **Create API Key**
5. 复制 API Key

**详细教程**: [查看](../models/deepseek.md)

---

## ⚙️ 高级配置

### 多模型配置

```json
{
  "models": {
    "zhipu": {
      "apiKey": "智谱 API_KEY",
      "modelId": "glm-4-flash",
      "enabled": true
    },
    "bailian": {
      "apiKey": "阿里云 API_KEY",
      "modelId": "qwen-plus",
      "enabled": true
    },
    "deepseek": {
      "apiKey": "DeepSeek API_KEY",
      "modelId": "deepseek-chat",
      "enabled": false
    }
  },
  "defaultModel": "zhipu"
}
```

### 设置默认模型

```powershell
openclaw models default zhipu
```

---

## 🆘 常见问题

### Q1: API Key 无效？

**错误信息**:
```
Error: Invalid API Key
```

**解决方案**:
1. 检查 API Key 是否复制完整 (无空格)
2. 确认账户已完成实名认证
3. 确认账户有余额
4. 检查 API 服务是否开通

---

### Q2: 余额不足？

**错误信息**:
```
Error: Insufficient balance
```

**解决方案**:
1. 登录对应平台控制台
2. 充值 (建议先充 ¥10 测试)
3. 重试

---

### Q3: 连接超时？

**错误信息**:
```
Error: Connection timeout
```

**解决方案**:
1. 检查网络连接
2. 检查防火墙设置
3. 稍后重试

---

### Q4: 如何切换模型？

**解决方案**:

```powershell
# 查看可用模型
openclaw models list

# 切换默认模型
openclaw models default zhipu

# 或编辑配置文件
notepad "$env:USERPROFILE\.openclaw\config.json"
```

---

## 📊 配置检查清单

- [ ] 已注册模型平台账号
- [ ] 已完成实名认证
- [ ] 已获取 API Key
- [ ] 已充值 (至少 ¥10)
- [ ] 配置文件已保存
- [ ] 测试连接成功

---

## 💰 充值建议

| 使用强度 | 推荐充值 | 预计可用时间 |
|----------|----------|--------------|
| 轻度 (每天 10 次) | ¥10 | 1-2 个月 |
| 中度 (每天 50 次) | ¥50 | 1 个月 |
| 重度 (每天 200 次) | ¥100 | 1 个月 |

---

## 📚 下一步

配置完成后，继续下一步：[登录机器人](./step4-channel-login.md)

---

## 📞 获取帮助

- [模型配置指南](../models/README.md)
- [智谱 AI 教程](../models/zhipu-ai.md)
- [阿里云教程](../models/aliyun-bailian.md)
- [常见问题 FAQ](../../docs/FAQ.md)

---

[上一步：安装 OpenClaw](./step2-install-openclaw.md) | [返回 Windows 教程首页](./README.md) | [下一步：登录机器人 →](./step4-channel-login.md)
