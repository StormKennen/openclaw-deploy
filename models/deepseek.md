# 🎯 DeepSeek 模型配置

> 国产开源大模型，代码能力强

---

## 🏢 平台介绍

**DeepSeek** 是深度求索推出的大模型系列，以代码能力和开源著称。

**优势：**
- ✅ 代码生成能力强
- ✅ 价格适中
- ✅ 支持开源部署
- ✅ 逻辑推理优秀

---

## 🚀 注册流程

### 步骤 1: 访问官网

打开 [DeepSeek 官网](https://www.deepseek.com/)

![DeepSeek 首页](https://www.deepseek.com/assets/home.png)

### 步骤 2: 注册账号

1. 点击右上角 **注册**
2. 选择注册方式：
   - 手机号
   - 邮箱
   - GitHub 账号

![注册页面](https://www.deepseek.com/assets/register.png)

3. 完成验证

---

### 步骤 3: 获取 API Key

1. 登录后，点击 **API Platform**

![API 平台](https://www.deepseek.com/assets/api-platform.png)

2. 点击 **Create API Key**
3. 输入名称 (如：OpenClaw)
4. 点击 **Create**

5. **复制 API Key**

```
sk-abc123def456ghi789jkl012mno345pqr678
```

---

### 步骤 4: 充值

1. 点击 **Billing**
2. 选择充值金额
3. 完成支付

---

## 🔧 OpenClaw 配置

### 配置文件

编辑 `~/.openclaw/config.json`:

```json
{
  "models": {
    "deepseek": {
      "apiKey": "sk-abc123def456ghi789jkl012mno345pqr678",
      "modelId": "deepseek-chat",
      "enabled": true
    }
  }
}
```

---

## 💰 价格说明

### DeepSeek-V2

| 项目 | 价格 |
|------|------|
| 输入 | ¥1 / 1M tokens |
| 输出 | ¥2 / 1M tokens |
| 上下文 | 32K tokens |

### 每月花费估算

**假设每天使用：**
- 输入：10K tokens
- 输出：5K tokens

**每月花费：**
```
输入：10K × 30 × ¥1/1M = ¥0.3
输出：5K × 30 × ¥2/1M = ¥0.3
总计：¥0.6/月
```

---

## 🎯 模型选择

| 模型 | 适用场景 |
|------|----------|
| deepseek-chat | 日常对话 (推荐) |
| deepseek-coder | 代码生成 |
| deepseek-vision | 图像理解 |

---

## 🆘 常见问题

### Q: API 调用失败？

**A**: 
- 检查 API Key
- 确认有余额
- 查看错误信息

---

## 📚 参考资源

- [DeepSeek 官网](https://www.deepseek.com/)
- [API 文档](https://platform.deepseek.com/api-docs/)
- [GitHub](https://github.com/deepseek-ai)

---

[返回主页](../README.md) | [上一篇：阿里云百炼](./aliyun-bailian.md)
