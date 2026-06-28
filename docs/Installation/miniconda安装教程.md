# Miniconda 简介与安装教程

> 适合对象：Python 初学者、Django/数据分析/机器学习项目开发者，以及需要管理不同 Python 版本的人。
>
> 官网安装链接：https://www.anaconda.com/docs/getting-started/miniconda/install/overview

---

## 1. Miniconda 是什么？

Miniconda 是一个轻量级的 Python 环境管理工具。

它主要包含：

```text
Python
conda 包管理器
pip
少量基础依赖包
```

简单理解：

```text
Anaconda = Python + conda + 很多预装库
Miniconda = Python + conda + 最少基础工具
```

Miniconda 的特点是：

- 安装包体积小
- 默认安装的库少
- 更灵活
- 适合自己按项目安装需要的包
- 方便管理多个 Python 环境

---

## 2. Miniconda 有什么用？

Miniconda 最大的作用是：

> 管理不同项目的 Python 环境，避免版本冲突。

例如：

项目 A 需要：

```text
Python 3.10
Django 5.0
```

项目 B 需要：

```text
Python 3.8 旧版本依赖包
```

使用 Miniconda 后，可以分别创建环境：

```bash
conda create -n django_env python=3.10
conda create -n old_project python=3.8
```

这样每个项目之间互不影响。

---

## 3. Miniconda 和 Anaconda 的区别

| 对比 | Miniconda | Anaconda |
|---|---|---|
| 体积 | 小 | 大 |
| 默认安装包 | 很少 | 很多 |
| 灵活性 | 高 | 一般 |
| 安装速度 | 快 | 慢 |

---

# 4. macOS 安装 Miniconda

macOS 有两种常见安装方式：

1. 图形界面安装
2. 命令行安装

推荐使用命令行安装，因为更容易控制安装路径。

---

## 4.1 macOS 方法一：图形界面安装

适合不熟悉命令行的用户。

### 步骤

1. 打开 Anaconda 官方下载页面。
2. 找到 **Miniconda Installer**。
3. 根据自己的 Mac 芯片选择版本：
   - Apple Silicon：M1 / M2 / M3 / M4
   - Intel：Intel 芯片
4. 下载 `.pkg` 安装包。
5. 双击 `.pkg` 文件。
6. 按照安装向导点击 Continue / Agree / Install。
7. 安装完成后打开 Terminal。
8. 输入下面命令验证：

```bash
conda --version
```


```bash
conda 26.x.x
```

---

## 4.2 macOS 方法二：命令行安装，推荐

### 第一步：下载 Miniconda 安装脚本

Apple Silicon Mac 使用：

```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
```

Intel Mac 使用：

```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
```

---

### 第二步：运行安装脚本

Apple Silicon Mac：

```bash
bash Miniconda3-latest-MacOSX-arm64.sh
```

Intel Mac：

```bash
bash Miniconda3-latest-MacOSX-x86_64.sh
```

安装过程中一般这样操作：

```text
按 Enter 阅读协议
输入 yes 同意协议
安装路径一般直接按 Enter
是否初始化 conda，输入 yes
```

默认安装路径一般是：

```bash
/Users/你的用户名/miniconda3
```

例如：

```bash
/Users/wangjiayi/miniconda3
```

---

### 第三步：让配置生效

安装完成后，可以关闭 Terminal 再重新打开。

也可以直接执行：

```bash
source ~/.zshrc
```

这个命令的意思是：

> 重新加载 zsh 配置文件，让 conda 命令立即生效。

---

### 第四步：验证安装

```bash
conda --version
```

或者：

```bash
conda list
```

如果能看到 conda 版本，或者显示一堆已安装的包，就说明安装成功。

---

# 5. Windows 安装 Miniconda

Windows 也有两种安装方式：

1. 图形界面安装，推荐新手使用
2. 命令行安装，适合进阶用户

---

## 5.1 Windows 方法一：图形界面安装，推荐

### 第一步：下载安装包

1. 打开 Anaconda 官方下载页面。
2. 找到 **Miniconda Installer**。
3. 下载 `.exe` 安装包。

---

### 第二步：运行安装程序

1. 打开 Downloads 下载文件夹。
2. 双击 Miniconda 的 `.exe` 安装文件。
3. 点击 Next。
4. 阅读协议后点击 I Agree。

---

### 第三步：选择安装路径

建议安装路径不要有中文、空格或特殊符号。

推荐类似：

```text
C:\Users\你的用户名\miniconda3
```

例如：

```text
C:\Users\xxxx\miniconda3
```

不太推荐：

```text
C:\Program Files\miniconda3
```

因为 `Program Files` 中间有空格，有些工具可能会出现兼容问题。

---

### 第四步：安装选项怎么选？

安装时可能会看到类似选项：

```text
Add Miniconda3 to my PATH environment variable
Register Miniconda3 as my default Python
```

新手建议：

- 不勾选 Add Miniconda3 to PATH
- 可以勾选 Register Miniconda3 as my default Python

原因：

- 不把 Miniconda 加入 PATH 可以减少和系统 Python 的冲突
- 后续使用 Anaconda Prompt 会更稳定

---

### 第五步：完成安装

点击 Install，等待安装完成，然后点击 Finish。

---

### 第六步：打开 Anaconda Prompt

安装完成后：

1. 点击 Windows 搜索栏。
2. 搜索：

```text
Anaconda Prompt
```

3. 打开它。

你可能会看到类似：

```text
(base) C:\Users\你的用户名>
```

这里的 `(base)` 表示当前进入了 conda 的 base 环境。

---

### 第七步：验证安装

在 Anaconda Prompt 里输入：

```bash
conda --version
```

或者：

```bash
conda list
```

如果能显示 conda 版本或包列表，说明安装成功。

---

## 5.2 Windows 方法二：命令行安装

这种方法适合对 PowerShell 或 Command Prompt 比较熟悉的人。

---

### 方法 A：PowerShell 下载

打开 PowerShell，输入：

```powershell
Invoke-WebRequest -Uri "https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe" -OutFile ".\Miniconda3-latest-Windows-x86_64.exe"
```

然后运行安装文件：

```powershell
.\Miniconda3-latest-Windows-x86_64.exe
```

之后按照图形界面安装步骤继续即可。

---

### 方法 B：Command Prompt 下载

打开 Command Prompt，输入：

```cmd
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe --output .\Miniconda3-latest-Windows-x86_64.exe
```

然后运行安装文件：

```cmd
Miniconda3-latest-Windows-x86_64.exe
```

---

## 5.3 Windows 常见问题

### 问题 1：安装后 conda 命令找不到

如果在普通 CMD 或 PowerShell 里输入：

```bash
conda --version
```

显示：

```text
conda is not recognized
```

先不要急。新手建议直接打开：

```text
Anaconda Prompt
```

然后在 Anaconda Prompt 里运行：

```bash
conda --version
```

---

# 6. 安装后常用 conda 命令

## 查看 conda 版本

```bash
conda --version
```

---

## 查看 Python 版本

```bash
python --version
```

---

## 查看当前有哪些环境

```bash
conda info --envs
```

你可能会看到：

```text
base                  *  /Users/xxxx/miniconda3
```

其中 `*` 表示当前正在使用的环境。

---

## 创建新环境

例如创建 Python 3.10 环境：

```bash
$ conda create -n myenv python=3.10
```

含义：

```text
myenv 是环境名字
python=3.10 是 Python 版本
```

---

## 激活环境

```bash
$ conda activate myenv
```

激活后，终端前面通常会出现：

```text
(myenv)
```

---

## 退出环境

```bash
$ conda deactivate
```

---

## 安装包

使用 conda 安装：

```bash
$ conda install numpy pandas
```

使用 pip 安装：

```bash
$ pip install django
```

---

## 查看所有虚拟环境
```bash
$ conda env list
```

---

## 查看当前环境安装了哪些包

```bash
$ conda list
```

---

查看当前环境安装了哪些包

## 删除环境

```bash
$ conda remove -n [虚拟环境名称] --all
```

## 删除虚拟环境

```bash
$ conda remove -n [虚拟环境名称]
```

总结：

> Miniconda 主要用来管理 Python 环境，避免不同项目之间的版本冲突。

---

# 10. 官方参考资料

- Miniconda 安装总览：https://www.anaconda.com/docs/getting-started/miniconda/install/overview
- macOS 命令行安装：https://www.anaconda.com/docs/getting-started/miniconda/install/mac-cli-install
- macOS 图形界面安装：https://www.anaconda.com/docs/getting-started/miniconda/install/mac-gui-install
- Windows 图形界面安装：https://www.anaconda.com/docs/getting-started/miniconda/install/windows-gui-install
- Windows 命令行安装：https://www.anaconda.com/docs/getting-started/miniconda/install/windows-cli-install
