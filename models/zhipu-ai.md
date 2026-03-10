# 📚 智谱 AI 模型配置

> 最便宜的国产大模型，¥0.1/1M tokens

---

## 🏢 平台介绍

**智谱 AI** 是清华大学知识工程实验室孵化的 AI 公司，提供 GLM 系列大模型。

**优势：**
- ✅ 价格最低 (¥0.1/1M tokens)
- ✅ 中文优化好
- ✅ 128K 大上下文
- ✅ 响应速度快

---

## 🚀 注册流程

### 步骤 1: 访问官网

打开 [智谱 AI 开放平台](https://open.bigmodel.cn/)

![智谱 AI 首页](https://open.bigmodel.cn/assets/home.png)

### 步骤 2: 注册账号

1. 点击右上角 **注册**
2. 选择注册方式：
   - 手机号注册 (推荐)
   - 微信快捷登录

![注册页面](https://open.bigmodel.cn/assets/register.png)

3. 填写手机号，获取验证码
4. 设置密码
5. 完成注册

---

### 步骤 3: 实名认证 ⚠️

> ⚠️ **重要**: 必须实名认证才能充值和使用 API

1. 登录后，点击右上角头像
2. 选择 **账户设置** → **实名认证**

![实名认证](https://open.bigmodel.cn/assets/verification.png)

3. 选择认证类型：
   - **个人认证**: 身份证
   - **企业认证**: 营业执照

4. 上传身份证照片
5. 填写真实姓名和身份证号
6. 提交审核 (通常几分钟内通过)

---

### 步骤 4: 充值

1. 点击左侧 **充值管理**

![充值页面](https://open.bigmodel.cn/assets/recharge.png)

2. 选择充值金额：
   - 首次建议充值 **¥10** (体验用)
   - 日常使用建议 **¥50-100**

3. 选择支付方式：
   - 微信支付
   - 支付宝

4. 完成支付

---

### 步骤 5: 创建 API Key

1. 点击左侧 **API Key 管理**

![API Key 管理](https://open.bigmodel.cn/assets/api-key.png)

2. 点击 **添加 API Key**
3. 填写名称 (如：OpenClaw)
4. 选择权限：**全部权限**
5. 点击 **确定**

6. **复制 API Key** (只显示一次，务必保存！)

```
abc123def456ghi789jkl012mno345pqr678
```

---

## 🔧 OpenClaw 配置

### 方式 1: 配置向导

```bash
# 运行配置向导
openclaw onboard

# 选择模型提供商
# 选择 智谱 AI
# 粘贴 API Key
```

### 方式 2: 手动配置

编辑 `~/.openclaw/config.json`:

```json
{
  "models": {
    "zhipu": {
      "apiKey": "abc123def456ghi789jkl012mno345pqr678",
      "modelId": "glm-4-flash",
      "enabled": true
    }
  }
}
```

---

## 💰 价格说明

### GLM-4-Flash (推荐)

| 项目 | 价格 |
|------|------|
| 输入 | ¥0.1 / 1M tokens |
| 输出 | ¥0.1 / 1M tokens |
| 上下文 | 128K tokens |

### 价格对比

**假设每天使用：**
- 输入：10K tokens
- 输出：5K tokens

**每月花费：**
```
(10K + 5K) × 30 天 = 450K tokens/月
450K × ¥0.1/1M = ¥0.045/月
```

> 💡 **结论**: 每天正常使用，每月不到 ¥1！

---

## 📊 用量监控

### 查看用量

1. 登录控制台
2. 点击 **用量统计**

![用量统计](https://open.bigmodel.cn/assets/usage.png)

3. 查看：
   - 今日用量
   - 本月用量
   - 余额

### 设置告警

1. 点击 **告警设置**
2. 设置阈值：
   - 日用量告警：¥5
   - 月用量告警：¥50
3. 配置通知方式：短信/邮件

---

## 🎯 模型选择

### 推荐模型

| 模型 | 价格 | 适用场景 |
|------|------|----------|
| **GLM-4-Flash** | ¥0.1/1M | 日常对话、文档总结 (推荐) |
| GLM-4 | ¥0.1/1K | 复杂任务、代码生成 |
| GLM-3-Turbo | ¥0.005/1K | 简单任务、快速响应 |

### 配置示例

```json
{
  "models": {
    "zhipu": {
      "apiKey": "你的 API_KEY",
      "modelId": "glm-4-flash"  // 推荐
    }
  }
}
```

---

## 🆘 常见问题

### Q: 实名认证失败？

**A**: 
- 检查身份证照片是否清晰
- 确保姓名和身份证号一致
- 联系在线客服

### Q: 充值后余额不显示？

**A**: 
- 刷新页面
- 退出重登
- 联系客服查询

### Q: API 调用失败？

**A**: 
- 检查 API Key 是否正确
- 确认账户有余额
- 查看错误信息

### Q: 如何开发票？

**A**: 
- 点击 **发票管理**
- 填写开票信息
- 提交申请

---

## 📚 参考资源

- [智谱 AI 开放平台](https://open.bigmodel.cn/)
- [API 文档](https://open.bigmodel.cn/dev/api)
- [价格说明](https://open.bigmodel.cn/dev/pricing)
- [使用示例](https://open.bigmodel.cn/dev/example)

---

[返回主页](../README.md) | [上一篇：模型总览](./README.md) | [下一篇：阿里云百炼](./aliyun-bailian.md)
