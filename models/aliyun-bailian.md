# ☁️ 阿里云百炼模型配置

> 企业级服务，通义千问最新模型

---

## 🏢 平台介绍

**阿里云百炼** 是阿里云推出的大模型开发平台，提供通义千问系列模型。

**优势：**
- ✅ 企业级服务，稳定可靠
- ✅ 通义千问最新模型
- ✅ 阿里云生态集成
- ✅ 技术支持完善

---

## 🚀 注册流程

### 步骤 1: 访问官网

打开 [阿里云百炼](https://bailian.console.aliyun.com/)

![阿里云百炼首页](https://bailian.console.aliyun.com/assets/home.png)

### 步骤 2: 注册阿里云账号

1. 点击右上角 **免费注册**
2. 选择注册方式：
   - 手机号注册
   - 支付宝扫码登录

![注册页面](https://bailian.console.aliyun.com/assets/register.png)

3. 填写信息完成注册

---

### 步骤 3: 实名认证 ⚠️

> ⚠️ **重要**: 必须实名认证才能使用 API

1. 登录后，访问 [账号管理](https://account.aliyun.com/)
2. 点击 **实名认证**

![实名认证](https://bailian.console.aliyun.com/assets/verification.png)

3. 选择认证类型：
   - **个人认证**: 身份证
   - **企业认证**: 营业执照

4. 按提示完成认证
5. 等待审核 (通常几分钟)

---

### 步骤 4: 开通百炼服务

1. 访问 [百炼控制台](https://bailian.console.aliyun.com/)
2. 点击 **开通服务**

![开通服务](https://bailian.console.aliyun.com/assets/activate.png)

3. 阅读并同意服务协议
4. 点击 **立即开通**

---

### 步骤 5: 充值

1. 访问 [费用中心](https://usercenter2.aliyun.com/)
2. 点击 **充值**

![充值页面](https://bailian.console.aliyun.com/assets/recharge.png)

3. 选择充值金额：
   - 首次建议 **¥50** (体验用)
   - 日常使用建议 **¥100-200**

4. 选择支付方式完成支付

---

### 步骤 6: 创建 API Key

1. 访问 [API-KEY 管理](https://bailian.console.aliyun.com/?apiKey=1#/api-key)

![API Key 管理](https://bailian.console.aliyun.com/assets/api-key.png)

2. 点击 **创建新的 API-KEY**
3. 输入名称 (如：OpenClaw)
4. 点击 **确定**

5. **复制 API Key** (只显示一次！)

```
sk-abc123def456ghi789jkl012mno345pqr678stu901vwx234
```

---

## 🔧 OpenClaw 配置

### 方式 1: 配置向导

```bash
openclaw onboard

# 选择 阿里云百炼
# 粘贴 API Key
```

### 方式 2: 手动配置

编辑 `~/.openclaw/config.json`:

```json
{
  "models": {
    "bailian": {
      "apiKey": "sk-abc123def456ghi789jkl012mno345pqr678stu901vwx234",
      "modelId": "qwen-plus",
      "enabled": true
    }
  }
}
```

---

## 💰 价格说明

### 通义千问系列

| 模型 | 输入价格 | 输出价格 | 上下文 | 推荐度 |
|------|----------|----------|--------|--------|
| **Qwen-Plus** | ¥2/1M | ¥6/1M | 32K | ⭐⭐⭐⭐⭐ |
| Qwen-Turbo | ¥0.5/1M | ¥1.5/1M | 8K | ⭐⭐⭐⭐ |
| Qwen-Max | ¥20/1M | ¥60/1M | 32K | ⭐⭐⭐ |
| Qwen-Long | ¥0.5/1M | ¥2/1M | 10M | ⭐⭐⭐⭐ |

### 价格对比

**假设每天使用：**
- 输入：10K tokens
- 输出：5K tokens

**每月花费 (Qwen-Plus)：**
```
输入：10K × 30 天 × ¥2/1M = ¥0.6
输出：5K × 30 天 × ¥6/1M = ¥0.9
总计：¥1.5/月
```

---

## 📊 用量监控

### 查看用量

1. 登录 [百炼控制台](https://bailian.console.aliyun.com/)
2. 点击 **用量统计**

![用量统计](https://bailian.console.aliyun.com/assets/usage.png)

3. 查看：
   - 今日调用次数
   - 本月用量
   - 费用明细

### 设置告警

1. 访问 [费用中心](https://usercenter2.aliyun.com/)
2. 点击 **告警设置**
3. 设置阈值：
   - 日用量：¥10
   - 月用量：¥100
4. 配置通知方式

---

## 🎯 模型选择

### 推荐模型

| 场景 | 推荐模型 | 理由 |
|------|----------|------|
| 日常对话 | Qwen-Plus | 性价比最高 |
| 快速响应 | Qwen-Turbo | 速度最快 |
| 复杂任务 | Qwen-Max | 能力最强 |
| 长文档 | Qwen-Long | 10M 上下文 |

### 配置示例

```json
{
  "models": {
    "bailian": {
      "apiKey": "你的 API_KEY",
      "modelId": "qwen-plus"  // 推荐
    }
  }
}
```

---

## 🆘 常见问题

### Q: 实名认证失败？

**A**: 
- 检查身份证照片清晰度
- 确保信息一致
- 联系客服

### Q: API 调用失败？

**A**: 
- 检查 API Key 是否正确
- 确认服务已开通
- 查看账户余额

### Q: 如何开发票？

**A**: 
- 访问费用中心
- 点击发票管理
- 填写开票信息

---

## 📚 参考资源

- [阿里云百炼](https://bailian.console.aliyun.com/)
- [API 文档](https://help.aliyun.com/zh/model-studio/)
- [价格说明](https://help.aliyun.com/zh/model-studio/pricing)
- [通义千问](https://tongyi.aliyun.com/)

---

[返回主页](../README.md) | [上一篇：智谱 AI](./zhipu-ai.md) | [下一篇：DeepSeek](./deepseek.md)
