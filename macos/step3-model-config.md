# 💰 步骤 3：配置 AI 模型

> macOS 系统模型配置教程

**难度**: ⭐⭐⭐ | **预计时间**: 15 分钟

---

## 🎯 模型选择

| 模型 | 价格 | 推荐度 |
|------|------|--------|
| 智谱 GLM-4-Flash | ¥0.1/1M | ⭐⭐⭐⭐⭐ |
| 阿里云 Qwen-Plus | ¥2/1M | ⭐⭐⭐⭐ |
| DeepSeek-V2 | ¥1/1M | ⭐⭐⭐⭐ |

---

## 🚀 配置步骤

### 方式 1: 配置向导

```bash
# 运行向导
openclaw onboard

# 按提示选择模型并输入 API Key
```

### 方式 2: 手动配置

```bash
# 编辑配置文件
nano ~/.openclaw/config.json
```

添加配置：

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

保存：`Ctrl + O` → 回车 → `Ctrl + X`

---

## 🔑 获取 API Key

- **智谱 AI**: https://open.bigmodel.cn/
- **阿里云**: https://bailian.console.aliyun.com/
- **DeepSeek**: https://platform.deepseek.com/

---

## 📚 下一步

[登录机器人 →](./step4-channel-login.md)

---

[上一步：安装 OpenClaw](./step2-install-openclaw.md) | [返回 macOS 教程首页](./README.md) | [下一步：登录机器人 →](./step4-channel-login.md)
