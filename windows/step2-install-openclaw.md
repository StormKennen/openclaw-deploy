# 🦞 步骤 2：安装 OpenClaw

> Windows 系统 OpenClaw 安装教程

**难度**: ⭐⭐ | **预计时间**: 5 分钟

---

## 📋 前置要求

- ✅ 已安装 Node.js 22+
- ✅ 已配置 npm 镜像 (推荐)
- ✅ 稳定的网络连接

---

## 🚀 安装步骤

### 步骤 1: 以管理员身份运行 PowerShell

1. 按 `Win + X` 键
2. 选择 **Windows PowerShell (管理员)** 或 **终端 (管理员)**

![以管理员身份运行](https://learn.microsoft.com/zh-cn/windows/powershell/media/run-as-admin.png)

---

### 步骤 2: 安装 OpenClaw

在 PowerShell 中输入：

```powershell
npm install -g openclaw@latest
```

**参数说明**:
- `-g`: 全局安装 (所有用户可用)
- `@latest`: 安装最新版本

**安装过程**:
```
> openclaw@2026.3.8 install
> node scripts/install.js

added 150 packages in 30s
```

---

### 步骤 3: 验证安装

安装完成后，输入：

```powershell
openclaw --version
```

应该显示版本号，如：`OpenClaw 2026.3.8`

---

### 步骤 4: 查看帮助

```powershell
openclaw --help
```

显示可用命令列表：

```
OpenClaw CLI - AI 私人助理网关

用法:
  openclaw <命令> [选项]

命令:
  onboard          配置向导
  gateway          启动网关服务
  channels         渠道管理
  models           模型配置
  logs             查看日志
  status           查看状态
  help             显示帮助
```

---

## ⚙️ 可选配置

### 配置 npm 全局目录 (避免权限问题)

```powershell
# 创建全局目录
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.npm-global"

# 配置 npm
npm config set prefix "$env:USERPROFILE\.npm-global"

# 添加到环境变量
[Environment]::SetEnvironmentVariable(
  "Path",
  "$env:USERPROFILE\.npm-global;$env:Path",
  "User"
)

# 重启 PowerShell 生效
```

---

## 🆘 常见问题

### Q1: 权限错误 EACCES？

**错误信息**:
```
npm ERR! Error: EACCES: permission denied
```

**解决方案 1**: 使用管理员权限
```powershell
# 以管理员身份运行 PowerShell
npm install -g openclaw@latest
```

**解决方案 2**: 配置 npm 目录
```powershell
# 配置全局目录 (见上方可选配置)
```

---

### Q2: 安装超时或失败？

**错误信息**:
```
npm ERR! network timeout at: https://registry.npmjs.org/
```

**解决方案**:

1. **使用国内镜像**
   ```powershell
   npm config set registry https://registry.npmmirror.com
   npm install -g openclaw@latest
   ```

2. **清除缓存**
   ```powershell
   npm cache clean --force
   npm install -g openclaw@latest
   ```

3. **检查网络**
   - 确保网络连接正常
   - 尝试关闭代理/VPN

---

### Q3: 版本不兼容？

**错误信息**:
```
Error: Node.js version must be 22 or higher
```

**解决方案**:

1. **查看当前版本**
   ```powershell
   node --version
   ```

2. **升级 Node.js**
   - 访问 [Node.js 官网](https://nodejs.org/)
   - 下载并安装最新版本

3. **或使用 nvm-windows**
   ```powershell
   # 安装 nvm-windows
   winget install CoreyButler.NVMforWindows

   # 安装 Node.js 22
   nvm install 22
   nvm use 22
   ```

---

### Q4: 如何卸载 OpenClaw？

**解决方案**:

```powershell
# 卸载全局包
npm uninstall -g openclaw

# 删除配置目录
Remove-Item -Recurse -Force "$env:USERPROFILE\.openclaw"

# 验证卸载
openclaw --version  # 应该显示命令未找到
```

---

## 📊 安装检查清单

- [ ] Node.js 22+ 已安装
- [ ] npm 镜像已配置
- [ ] PowerShell 以管理员身份运行
- [ ] OpenClaw 安装成功
- [ ] 版本号显示正常
- [ ] help 命令可用

---

## 📚 下一步

安装完成后，继续下一步：[配置 AI 模型](./step3-model-config.md)

---

## 📞 获取帮助

- [OpenClaw 官方文档](https://docs.openclaw.ai/)
- [GitHub Issues](https://github.com/openclaw/openclaw/issues)
- [Discord 社区](https://discord.com/invite/clawd)
- [常见问题 FAQ](../../docs/FAQ.md)

---

[上一步：安装 Node.js](./step1-install-nodejs.md) | [返回 Windows 教程首页](./README.md) | [下一步：配置 AI 模型 →](./step3-model-config.md)
