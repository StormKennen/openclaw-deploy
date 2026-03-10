# 📦 步骤 1：安装 Node.js

> Windows 系统详细安装教程

**难度**: ⭐ | **预计时间**: 10 分钟

---

## 📋 系统要求

- **操作系统**: Windows 10/11 (64 位)
- **内存**: 至少 2GB RAM
- **磁盘**: 至少 200MB 可用空间

---

## 🚀 安装步骤

### 方式 1: 官网安装包 (推荐新手)

#### 步骤 1: 下载 Node.js

1. 打开浏览器，访问 [Node.js 官网](https://nodejs.org/)

![Node.js 官网](https://nodejs.org/static/images/logo.svg)

2. 点击 **绿色按钮** 下载 LTS 版本 (长期支持版)
   - 推荐版本：Node.js 22.x LTS
   - 文件格式：`.msi` 安装包

#### 步骤 2: 安装 Node.js

1. 双击下载的 `.msi` 文件

![安装向导](https://nodejs.org/static/images/install-windows-1.png)

2. 点击 **Next** 继续

3. 接受许可协议
   - 勾选 **I accept the terms**
   - 点击 **Next**

4. 选择安装路径
   - 默认：`C:\Program Files\nodejs\`
   - 建议保持默认
   - 点击 **Next**

![安装路径](https://nodejs.org/static/images/install-windows-2.png)

5. **重要**: 自定义安装选项
   - ✅ **Automatically install the necessary tools** (自动安装必要工具)
   - 这个选项会安装 npm 和必要开发工具
   - 点击 **Next**

6. 点击 **Install** 开始安装

7. 等待安装完成

8. 点击 **Finish** 完成安装

#### 步骤 3: 验证安装

1. 按 `Win + R` 键，输入 `cmd`，回车

2. 在命令提示符中输入：

```cmd
node --version
```

应该显示版本号，如：`v22.x.x`

3. 输入：

```cmd
npm --version
```

应该显示版本号，如：`10.x.x`

![验证安装](https://nodejs.org/static/images/verify-windows.png)

✅ **如果显示版本号，说明安装成功！**

---

### 方式 2: 使用 Winget (适合高级用户)

```powershell
# 打开 PowerShell (管理员)
winget install OpenJS.NodeJS.LTS

# 验证
node --version
npm --version
```

---

### 方式 3: 使用 Chocolatey

```powershell
# 安装 Chocolatey (如果未安装)
Set-ExecutionPolicy Bypass -Scope Process -Force
iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

# 安装 Node.js
choco install nodejs-lts -y

# 验证
node --version
npm --version
```

---

## ⚙️ 配置 npm 镜像 (加速下载)

### 临时使用镜像

```cmd
npm config set registry https://registry.npmmirror.com
```

### 永久配置镜像

1. 编辑用户配置文件

```cmd
notepad %USERPROFILE%\.npmrc
```

2. 添加以下内容：

```
registry=https://registry.npmmirror.com
```

3. 保存文件

### 验证配置

```cmd
npm config get registry
```

应该显示：`https://registry.npmmirror.com`

---

## 🆘 常见问题

### Q1: 安装失败，提示权限错误？

**解决方案**:
1. 右键安装包 → **以管理员身份运行**
2. 或关闭杀毒软件后重试

---

### Q2: node 命令无法识别？

**错误信息**: `'node' 不是内部或外部命令`

**解决方案**:

1. **重启命令行窗口**
   - 关闭所有 cmd/PowerShell 窗口
   - 重新打开

2. **检查环境变量**
   - 右键 **此电脑** → **属性**
   - 点击 **高级系统设置**
   - 点击 **环境变量**
   - 在 **系统变量** 中找到 `Path`
   - 确保包含 `C:\Program Files\nodejs\`

3. **重新安装**
   - 卸载 Node.js
   - 重新下载安装

---

### Q3: npm 下载速度慢？

**解决方案**: 使用国内镜像

```cmd
# 使用淘宝镜像
npm config set registry https://registry.npmmirror.com

# 验证
npm config get registry
```

---

### Q4: 如何卸载 Node.js？

**解决方案**:

1. 打开 **控制面板** → **程序和功能**
2. 找到 **Node.js**
3. 右键 → **卸载**
4. 删除配置目录：
   ```cmd
   rmdir /s %USERPROFILE%\AppData\Roaming\npm
   rmdir /s %USERPROFILE%\AppData\Roaming\npm-cache
   ```

---

## 📚 下一步

安装完成后，继续下一步：[安装 OpenClaw](./step2-install-openclaw.md)

---

## 📞 获取帮助

- [Node.js 官方文档](https://nodejs.org/docs/)
- [npm 使用指南](https://docs.npmjs.com/)
- [常见问题 FAQ](../../docs/FAQ.md)

---

[返回 Windows 教程首页](./README.md) | [下一步：安装 OpenClaw →](./step2-install-openclaw.md)
