### Claude Code+*DeepSeek* V4 Pro安装教程

Deepseek官方文档：https://api-docs.deepseek.com/guides/agent_integrations/claude_code

DeepseekApi官网：https://platform.deepseek.com/usage

---

#### 1. 安装安装node.js

​		官网文档： https://nodejs.org/en/download

​		macOS安装Node.js

```bash
# Download and install nvm:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.5/install.sh | bash

# in lieu of restarting the shell
\. "$HOME/.nvm/nvm.sh"

# Download and install Node.js:
nvm install 24

# Verify the Node.js version:
node -v # Should print "v24.18.0".

# Verify npm version:
npm -v # Should print "11.16.0".
```

Windows安装Node.js

```bash
# Download and install Chocolatey:
powershell -c "irm https://community.chocolatey.org/install.ps1|iex"

# Download and install Node.js:
choco install nodejs --version="24.18.0"

# Verify the Node.js version:
node -v # Should print "v24.18.0".

# Verify npm version:
npm -v # Should print "11.16.0".

```

国内镜像：npm config set registry https://registry.npmmirror.com/ 

---

#### 2. Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

- After installation, run the following command. If the version number is displayed, the installation is successful:

```bash
claude --version
```

安装完成后给.claude.json文件添加 "hasCompletedOnboarding": true

```bash
echo '{ "hasCompletedOnboarding": true }' > ~/.claude.json
```

`"hasCompletedOnboarding": true` 是一个布尔开关，含义是：

> 告诉 Claude Code：「我已经完成了首次引导流程，不需要再做地区校验、账号登录等初始化步骤了」

---

#### 3.安装cc-switch

https://github.com/farion1231/cc-switch

 **macOS**

**Method 1: Install via Homebrew (Recommended)**

Install via Homebrew (Recommended)

```bash
brew install --cask cc-switch
```

Update:

```bash
brew upgrade --cask cc-switch
```

**Method 2: Manual Download**

Download `CC-Switch-v{version}-macOS.dmg` (recommended) or `.zip` from the [Releases](https://github.com/farion1231/cc-switch/releases) page.

> **Note**: CC Switch for macOS is code-signed and notarized by Apple. You can install and open it directly.

#### 4. 购买Deepseek api 

DeepseekApi官网：https://platform.deepseek.com/usage

#### 5. 配置cc-switch

1. 添加新的供应商
2. 选择DeepSeek
3. 添加API Key
4. 模型映射 deepseek-v4-pro[1m]

#### 6.打开Terminal

进入项目目录运行claude

```text
cd /path/to/my-project
claude
```

切换/查看模型：/model