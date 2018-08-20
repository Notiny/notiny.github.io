---
title: MAC tree 命令详解
date: 2018-08-20 14:27:02
tags: MAC
---

`MAC` 下默认没有 `tree` 命令, 不过可以使用 `find` 命令模拟出 `tree` 命令的效果:

``` bash
# 显示当前目录
$ find . -print | sed -e 's;[^/]*/;|——;g; s;——|; |;g'
```

设置别名快速执行该命令

``` bash
$ cd ~
$ vim .bash_profile
# 在 .bash_profile 内写入以下命令, 保存并退出
$
$ alias tree="find . -print | sed -e 's;[^/]*/;|——;g; s;——|; |;g'"
$
# 直接运行 tree 命令
$ tree
```

除了使用 `find` 模拟 `tree` 外, 还可以使用 `homebrew` 安装 `tree` 命令。

<!--more-->

## 安装

安装 `tree` 相当简单。然而在安装前，您必须检查电脑中是否已安装 `homebrew` 包管理器

- [homebrew](https://brew.sh/index_zh-cn.html)

如果您的电脑中尚未安装 `homebrew` 包管理器，先安装 `homebrew` 包管理器。

``` bash
# 将以下命令粘贴至终端进行安装 brew
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

关于 `homebrew` 的使用请移驾至: [HomeBrew](https://brew.sh/index_zh-cn.html)

如果您的电脑中已经安装了 `homebrew` 包管理器，那么接下来只需要使用 `brew` 即可完成 `tree` 的安装。

``` bash
# brew 安装 tree
$ brew install tree
```

## tree 参数详解

``` bash
# 彩色显示 1 层目录
$ tree -C -L 1
```

### 常用参数

`-a` 显示所有文件和目录 (默认显示所有的文件和目录)
`-L n` 只显示 n 层目录 (n 为数字)
`-d` 只显示目录名称
`-f` 显示完整的相对路径以及名称
`-s` 显示文件或目录大小。
`-r` 以相反次序排列
`-t` 用文件和目录的更改时间排序
`-C` 文件和目录加上色彩，便于区分各种类型。
`-dirsfirst` 目录显示在前,文件显示在后

### 更多参数

`-A` 使用 `ASNI` 绘图字符显示树状图而非以 `ASCII` 字符组合
`-D` 列出文件或目录的更改时间。
`-g` 列出文件或目录的所属群组名称，没有对应的名称时，则显示群组识别码。
`-N` 直接列出文件和目录名称，包括控制字符。
`-l` 如遇到性质为符号连接的目录，直接列出该连接所指向的原始目录。
`-u` 列出文件或目录的拥有者名称，没有对应的名称时，则显示用户识别码。
`-F` 在执行文件，目录，Socket，符号连接，管道名称名称，各自加上 "\*", "/", "=", "@", "|"号。
`-i` 不以阶梯状列出文件或目录名称。
`-I` 不显示符合范本样式的文件或目录名称。
`-n` 不在文件和目录清单加上色彩。
`-p` 列出权限标示。
`-P` 只显示符合范本样式的文件或目录名称。
`-q` 用"?"号取代控制字符，列出文件和目录名称。
`-x` 将范围局限在现行的文件系统中，若指定目录下的某些子目录，其存放于另一个文件系统上，则将该子目录予以排除在寻找范围外。
