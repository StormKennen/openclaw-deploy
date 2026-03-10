# 📦 步骤 1：安装 Node.js

> macOS 系统详细安装教程

**难度**: ⭐ | **预计时间**: 10 分钟

---

## 📋 系统要求

- **操作系统**: macOS 11+ (Big Sur 或更高)
- **芯片**: Intel 或 Apple Silicon (M1/M2/M3)
- **内存**: 至少 2GB RAM
- **磁盘**: 至少 200MB 可用空间

---

## 🚀 安装方式

### 方式 1: 官网安装包 (推荐新手)

#### 步骤 1: 下载 Node.js

1. 打开浏览器，访问 [Node.js 官网](https://nodejs.org/)
2. 点击 **绿色按钮** 下载 LTS 版本
3. 下载 `.pkg` 安装包

#### 步骤 2: 安装

1. 双击下载的 `.pkg` 文件
2. 按提示完成安装
3. 输入 Mac 密码确认

#### 步骤 3: 验证

打开 **终端** (Terminal)，输入：

```bash
node --version
npm --version
```

显示版本号即安装成功！

---

### 方式 2: 使用 Homebrew (推荐)

#### 步骤 1: 安装 Homebrew (如果未安装)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### 步骤 2: 安装 Node.js

```bash
brew install node@22
```

#### 步骤 3: 验证

```bash
node --version
npm --version
```

---

### 方式 3: 使用 nvm (多版本管理)

#### 步骤 1: 安装 nvm

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```

#### 步骤 2: 安装 Node.js

```bash
nvm install 22
nvm use 22
```

#### 步骤 3: 验证

```bash
node --version
npm --version
```

---

## ⚙️ 配置 npm 镜像

```bash
# 使用淘宝镜像
npm config set registry https://registry.npmmirror.com

# 验证
npm config get registry
```

---

## 🆘 常见问题

### Q1: 权限错误？

```bash
# 修复 npm 权限
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
```

### Q2: M1/M2芯片兼容性问题？

```bash
# 使用 Rosetta 2
arch -x86_64 zsh
# 然后重新安装
```

---

## 📚 下一步

[安装 OpenClaw →](./step2-install-openclaw.md)

---

[返回 macOS 教程首页](./README.md) | [下一步：安装 OpenClaw →](./step2-install-openclaw.md)
