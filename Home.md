# 导言

git 是一个分布式版本控制软件，最初由林纳斯·托瓦兹创作，于 2005 年以 GPL 许可协议发布。最初目的是为了更好地管理 Linux 内核开发而设计。如今 git 已经是最为流行的版本控制软件，被广泛地使用在诸多软件开发项目中。

git 和其他版本控制系统（如 CVS）有不小的差别，git 本身关心文件的整体性是否有改变，但多数的版本控制系统如 CVS 或 Subversion 系统则在乎文件内容的差异。git 并不保存每个文件的版本修订关系。因此查看一个文件的历史需要遍历各个 history 快照；git 隐式处理文件更名，即同名文件默认为其前身，如果没有同名文件则在前一个版本中搜索具有类似内容的文件。

但这样的特性反而让 git 更加使用用在软件开发项目中，举一个简单的例子：假设你正在开发一个软件，你的项目目录如下：

```txt
example/
├── main.py
└── lib/
    ├── lib1.py
    └── lib2.py
```

也就是有一个主函数 `main.py` 还有一个 `lib` 文件夹，其中包括了两个库文件。其他版本控制系统通常保存每个文件的历史记录，可能看起来是这样的

```txt
main.py:
    - 10s ago: bug fix
    - 10m ago: add a new function
    - 10h ago: initial

lib1.py:
    - 10s ago: bug fix
    - 10h ago: initial

lib2.py:
    - 10m ago: add a new function
    - 10h ago: initial
```

可以看到，实际上这个项目经历了三次操作

1. 10 小时前：`initial`，新增了`main.py, lib1.py, lib2.py` 三个文件
2. 10 分钟前：`add a new function`，修改了`main.py, lib2.py`文件
3. 10 秒钟前：`bug fix`，修改了`main.py, lib1.py`文件

尽管，按照文件的历史记录，我们可以轻易地回溯当前文件的历史版本。但在软件开发中，新增一个功能，或是修改一个 bug 往往涉及到多个文件，因此，我们其实更需要的是项目的历史记录，而不是单个文件的历史记录。具体来说，git 的历史记录看起来是下面这个样子的。

```txt
10s ago: bug fix
    - main.py (modify)
    - lib1.py (modify)

10m ago: add a new function
    - main.py (modify)
    - lib2.py (modify)

10h ago: initial
    - main.py (add)
    - lib1.py (add)
    - lib2.py (add)
```

不难发现，git 的这种特性更能够方便我们轻松地回溯软件开发的任意一个阶段。

此外，git 配合上远程仓库可以极大地方便多人协作开发。不仅可以实现代码共享，还可以实现保存开发记录，发布软件等等功能。

## 安装

### 在 Windows 上安装

官方版本可以在 Git 官方网站下载。 打开 https://git-scm.com/download/win ，下载会自动开始。要注意这是一个名为 Git for Windows 的项目（也叫做 msysGit），和 Git 是分别独立的项目.

### 在 macOS 上安装

在 Mac 上安装 Git 有多种方式。 最简单的方法是安装 Xcode Command Line Tools。 Mavericks （10.9） 或更高版本的系统中，在 Terminal 里尝试首次运行 'git' 命令即可。

```bash
git --version
```

如果没有安装过命令行开发者工具，将会提示你安装。

如果你想安装更新的版本，可以使用二进制安装程序。 官方维护的 macOS Git 安装程序可以在 Git 官方网站下载，网址为 https://git-scm.com/download/mac。

### 在 Linux 上安装

如果你想在 Linux 上用二进制安装程序来安装基本的 Git 工具，可以使用发行版包含的基础软件包管理工具来安装。 以 Fedora 为例，如果你在使用它（或与之紧密相关的基于 RPM 的发行版，如 RHEL 或 CentOS），你可以使用 dnf：

```bash
sudo dnf install git-all
```

如果你在基于 Debian 的发行版上，如 Ubuntu，请使用 apt：

```bash
sudo apt install git-all
```

要了解更多选择，Git 官方网站上有在各种 Unix 发行版的系统上安装步骤，网址为 https://git-scm.com/download/linux 。

## 使用教程

教程主要分为三个部分

-   Git 基础

    包括 git 的基本工作流程，以及对应的命令行操作

-   在 VSCode 中使用 Git

    介绍如何在 VSCode 中使用 git 的 gui

-   Gitea Web 界面操作

    主要介绍在 gitea web 界面的使用方法
