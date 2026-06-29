# Miniconda 简介与安装教程
> 官网链接：https://www.anaconda.com/docs/getting-started/miniconda/install/overview

---

## 1. Miniconda 是什么？

Miniconda 是一个轻量级的 Python 环境管理工具。

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

项目 A 需要：Python 3.10


项目 B 需要：Python 3.8 旧版本依赖包

使用 Miniconda，分别创建环境：

```bash
conda create -n projectA_env python=3.10
conda create -n projectB_env python=3.8
```
项目之间互不影响。

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

推荐使用命令行安装

---

## 4.1 macOS 方法一：图形界面安装
https://www.anaconda.com/docs/getting-started/miniconda/install/mac-gui-install

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

---

### 第三步：让配置生效

安装完成后，可以关闭 Terminal 重新打开。

或者

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

---

# 5. Windows 安装 Miniconda

Windows 也有两种安装方式：

1. 图形界面安装，推荐新手使用
2. 命令行安装，适合进阶用户

---

## 5.1 Windows 方法一：图形界面安装
https://www.anaconda.com/docs/getting-started/miniconda/install/windows-gui-install


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

# 6. 常用 conda 命令

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
$ conda create -n my_env python=3.10
```

含义：

```text
myenv 是环境名字
python=3.10 是 Python 版本
```

---

## 激活环境

```bash
$ conda activate my_env
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


## 删除环境

```bash
$ conda remove -n [虚拟环境名称] --all
```

## 删除虚拟环境

```bash
$ conda remove -n [虚拟环境名称]
```

---

# 10. 官方参考资料

- Miniconda 安装总览：https://www.anaconda.com/docs/getting-started/miniconda/install/overview
- macOS 命令行安装：https://www.anaconda.com/docs/getting-started/miniconda/install/mac-cli-install
- macOS 图形界面安装：https://www.anaconda.com/docs/getting-started/miniconda/install/mac-gui-install
- Windows 图形界面安装：https://www.anaconda.com/docs/getting-started/miniconda/install/windows-gui-install
- Windows 命令行安装：https://www.anaconda.com/docs/getting-started/miniconda/install/windows-cli-install