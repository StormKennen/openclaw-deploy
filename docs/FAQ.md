# ❓ 常见问题 FAQ

> OpenClaw 部署和使用过程中的高频问题

---

## 📦 安装问题

### Q1: npm 安装失败怎么办？

**错误信息**: `npm ERR! code EACCES`

**解决方案**:

**Windows**:
```powershell
# 以管理员身份运行 PowerShell
npm install -g openclaw@latest
```

**macOS/Linux**:
```bash
# 修复 npm 权限
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc

# 重新安装
npm install -g openclaw@latest
```

---

### Q2: Node.js 版本不兼容？

**错误信息**: `Unsupported Node.js version`

**解决方案**:

OpenClaw 需要 **Node.js 22+**

```bash
# 查看当前版本
node --version

# 升级 Node.js
# macOS (使用 Homebrew)
brew upgrade node

# Windows
# 访问 https://nodejs.org/ 下载最新版

# 或使用 nvm 管理多版本
nvm install 22
nvm use 22
```

---

### Q3: 如何卸载 OpenClaw？

**解决方案**:

```bash
# 卸载全局包
npm uninstall -g openclaw

# 删除配置目录
# Windows: C:\Users\<用户名>\.openclaw\
# macOS/Linux: ~/.openclaw/

rm -rf ~/.openclaw
```

---

## 🔑 模型配置问题

### Q4: API Key 无效？

**错误信息**: `Invalid API Key`

**解决方案**:

1. **检查 Key 是否正确**
   - 确保复制完整，无多余空格
   - 区分大小写

2. **确认账户状态**
   - 检查是否完成实名认证
   - 确认账户有余额

3. **验证 API 开通**
   - 登录控制台确认服务已开通
   - 检查 API Key 权限

---

### Q5: 哪个模型最便宜？

**推荐**:

| 模型 | 价格 | 推荐度 |
|------|------|--------|
| 智谱 GLM-4-Flash | ¥0.1/1M | ⭐⭐⭐⭐⭐ |
| DeepSeek-V2 | ¥1/1M | ⭐⭐⭐⭐ |
| 阿里云 Qwen-Plus | ¥2/1M | ⭐⭐⭐⭐ |

**详细对比**: [查看模型价格](../models/README.md)

---

### Q6: 如何切换模型？

**解决方案**:

编辑配置文件 `~/.openclaw/config.json`:

```json
{
  "models": {
    "zhipu": {
      "apiKey": "新 API Key",
      "modelId": "glm-4-flash",
      "enabled": true
    }
  }
}
```

然后重启 Gateway:

```bash
openclaw gateway restart
```

---

## 🤖 机器人问题

### Q7: 飞书机器人不回复？

**可能原因**:

1. **权限未审批**
   - 等待审批 (个人账号通常自动)
   - 企业账号联系管理员

2. **配置错误**
   - 检查 App ID 和 Secret
   - 确认机器人已添加到聊天

3. **Gateway 未运行**
   ```bash
   openclaw gateway status
   ```

---

### Q8: Telegram 机器人无法访问？

**解决方案**:

1. **检查网络**
   - Telegram 需要科学上网
   - 确保代理正常工作

2. **验证 Token**
   - 联系 @BotFather 检查 Token
   - 重新获取新 Token

3. **查看日志**
   ```bash
   openclaw logs --level error
   ```

---

### Q9: 企业微信/钉钉审核多久？

**答案**:

- **飞书**: 个人账号即时，企业 1-3 天
- **企业微信**: 1-3 天
- **钉钉**: 1-3 天
- **Telegram**: 无需审核

---

## ⚙️ 运行问题

### Q10: 端口被占用？

**错误信息**: `Port 18789 is already in use`

**解决方案**:

```bash
# 使用其他端口
openclaw gateway --port 18790

# 或查找占用端口的进程
# Windows
netstat -ano | findstr :18789

# macOS/Linux
lsof -i :18789
```

---

### Q11: Gateway 无法启动？

**排查步骤**:

1. **查看日志**
   ```bash
   openclaw logs
   ```

2. **检查配置**
   ```bash
   openclaw config get
   ```

3. **验证模型**
   - 确认 API Key 正确
   - 确认有余额

4. **重启服务**
   ```bash
   openclaw gateway restart
   ```

---

### Q12: 如何查看日志？

**命令**:

```bash
# 实时日志
openclaw logs

# 错误日志
openclaw logs --level error

# 指定行数
openclaw logs --lines 100
```

---

## 💰 费用问题

### Q13: 一个月大概花多少钱？

**估算**:

**轻度使用** (每天 10 次对话):
- 智谱 AI: ¥1-5/月
- 阿里云：¥5-10/月

**中度使用** (每天 50 次对话):
- 智谱 AI: ¥5-20/月
- 阿里云：¥20-50/月

**重度使用** (每天 200+ 次对话):
- 智谱 AI: ¥20-100/月
- 阿里云：¥100-200/月

---

### Q14: 如何设置用量告警？

**智谱 AI**:
1. 登录控制台
2. 点击 **告警设置**
3. 设置阈值 (如 ¥50/天)
4. 配置通知方式

**阿里云**:
1. 访问费用中心
2. 点击 **告警管理**
3. 创建告警规则

---

### Q15: 如何开发票？

**智谱 AI**:
- 控制台 → 发票管理 → 申请开票

**阿里云**:
- 费用中心 → 发票管理 → 申请

---

## 🔒 安全问题

### Q16: API Key 泄露了怎么办？

**紧急处理**:

1. **立即撤销**
   - 登录对应平台控制台
   - 删除/撤销泄露的 API Key

2. **重新创建**
   - 创建新的 API Key
   - 更新 OpenClaw 配置

3. **检查用量**
   - 查看是否有异常调用
   - 联系平台客服

---

### Q17: 数据是否安全？

**答案**:

✅ **安全**:
- OpenClaw 运行在你自己的设备上
- 数据不经过第三方服务器
- API 调用直接使用你的密钥

⚠️ **注意**:
- 保管好 API Key
- 定期更换密钥
- 不要提交到 GitHub

---

## 📱 移动端问题

### Q18: 支持手机部署吗？

**答案**:

目前 **不支持** 直接在手机上部署。

**替代方案**:
1. 在电脑/服务器部署 Gateway
2. 手机通过聊天 App 使用 (飞书/Telegram 等)

---

### Q19: 如何远程访问？

**方案 1: 使用内网穿透**

```bash
# 使用 ngrok
ngrok http 18789
```

**方案 2: 使用 Tailscale**

```bash
# 安装 Tailscale
tailscale up

# 使用 Tailscale IP 访问
```

**方案 3: 云服务器部署**

- 在云服务器部署 Gateway
- 通过公网 IP 访问

---

## 🆘 其他问题

### Q20: 如何更新 OpenClaw？

```bash
# 更新到最新版
npm install -g openclaw@latest

# 查看版本
openclaw --version

# 重启服务
openclaw gateway restart
```

---

### Q21: 如何备份配置？

```bash
# 备份配置文件
cp ~/.openclaw/config.json ~/.openclaw/config.json.backup

# 恢复配置
cp ~/.openclaw/config.json.backup ~/.openclaw/config.json
```

---

### Q22: 遇到问题如何求助？

**渠道**:

1. **查看文档**
   - [官方文档](https://docs.openclaw.ai/)
   - [本仓库教程](../README.md)

2. **社区求助**
   - [OpenClaw Discord](https://discord.com/invite/clawd)
   - [GitHub Issues](https://github.com/openclaw/openclaw/issues)

3. **提交 Issue**
   - 描述问题
   - 附上日志
   - 提供配置信息

---

[返回主页](../README.md)
