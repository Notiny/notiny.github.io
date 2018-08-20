---
title: hexo 使用文档
date: 2017-06-27 18:07:27
tags: hexo
---

`Hexo` 是一个快速、简洁且高效的博客框架。`Hexo` 使用 `Markdown`（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

# 特性

**超快速度**
`Node.js` 所带来的超快生成速度，让上百个页面在几秒内瞬间完成渲染。

**支持 Markdown**
`Hexo` 支持 `GitHub` `Flavored` `Markdown` 的所有功能，甚至可以整合 `Octopress` 的大多数插件。

**一键部署**
只需一条指令即可部署到 `GitHub Pages`, `Heroku` 或其他网站。

**丰富的插件**
`Hexo` 拥有强大的插件系统，安装插件可以让 `Hexo` 支持 `Jade`, `CoffeeScript`。

<!--more-->

# 安装

## 安装前必备

安装 `Hexo` 相当简单。然而在安装前，您必须检查电脑中是否已安装下列应用程序：

- [Node.js](https://nodejs.org/)
- [Git](http://git-scm.com/)

## 安装 `Hexo`

如果您的电脑中已经安装上述必备程序，那么接下来只需要使用 `npm` 即可完成 `Hexo` 的安装。

``` bash
npm install -g hexo-cli
```

如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。

### 安装 `Git`

- `Windows`：下载并安装 [msysgit](https://code.google.com/hosting/moved?project=msysgit).
- `Mac`：使用 [Homebrew](http://brew.sh/), [MacPorts](http://www.macports.org/) 或下载 [安装程序](https://code.google.com/p/git-osx-installer/) 安装。
- `Linux` (`Ubuntu`, `Debian`)：`sudo apt-get install git-core`
- `Linux` (`Fedora`, `Red Hat`, `CentOS`)：`sudo yum install git-core`

### 安装 Node.js

安装 `Node.js` 的最佳方式是使用 [nvm](https://github.com/creationix/nvm)。

**cURL:**

``` bash
curl https://raw.github.com/creationix/nvm/master/install.sh | sh  
```

**Wget:**

``` bash
wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
```

安装完成后，重启终端并执行下列命令即可安装 `Node.js`。

``` bash
nvm install 0.10
```

或者您也可以下载 [应用程序](https://nodejs.org/) 来安装。

### `npm` 安装 `Hexo`

所有必备的应用程序安装完成后，即可使用 `npm` 安装 `Hexo`。

``` bash
npm install -g hexo-cli  
```

# 开始使用

安装 `Hexo` 完成后，请执行下列命令，`Hexo` 将会在指定文件夹中新建所需要的文件。

``` bash
hexo init blog
cd blog
npm install
hexo server
```

## 目录结构

新建完成后，指定文件夹的目录如下：

``` bash
.
├── _config.yml
├── package.json
├── scaffolds
├── scripts
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

### `_config.yml`

网站的 [配置](http://hexo.io/zh-cn/docs/configuration.html) 信息，您可以在此配置大部分的参数。

### `package.json`

应用程序的信息。

`EJS`, `Stylus` 和 `Markdown renderer` 已默认安装，您可以自由移除。

``` bash
{  
  "name": "hexo-site",  
  "version": "",  
  "private": true,  
  "hexo": {  
    "version": ""  
  },  
  "dependencies": {  
    "hexo-renderer-ejs": "*",  
    "hexo-renderer-stylus": "*",  
    "hexo-renderer-marked": "*"  
  }  
}
```

### `scaffolds`

[模版](http://wiki.jikexueyuan.com/project/hexo-document/writing.html) 文件夹。当您新建文章时，`Hexo` 会根据 `scaffold` 来建立文件。

### `scripts`

[脚本](http://wiki.jikexueyuan.com/project/hexo-document/plugins.html) 文件夹。脚本是扩展 `Hexo` 最简易的方式，在此文件夹内的 `JavaScript` 文件会被自动执行。

### `source`

资源文件夹是存放用户资源的地方。除 `_posts` 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。`Markdown` 和 `HTML` 文件会被解析并放到 `public` 文件夹，而其他文件会被拷贝过去。

### `themes`

[主题](http://wiki.jikexueyuan.com/project/hexo-document/themes.html) 文件夹。Hexo 会根据主题来生成静态页面。

## 配置

您可以在 `_config.yml` 中修改大部份的配置。

### 网站

`title`: 网站标题
`subtitle`: 网站副标题
`description`: 网站描述
`author`: 您的名字
`language`: 网站使用的语言
`timezone`: 网站时区。Hexo 预设使用您电脑的时区。[时区列表](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)

### 网址

`url`: 网址
`root`: 网站根目录
`permalink`: [`:year/:month/:day/:title/`] 文章的 [永久链接](http://wiki.jikexueyuan.com/project/hexo-document/permalinks.html) 格式
`permalink_default`: 永久链接中各部分的默认值

### 目录

`source_dir`: [`source`] 资源文件夹，这个文件夹用来存放内容。
`public_dir`: [`public`] 公共文件夹，这个文件夹用于存放生成的站点文件。
`tag_dir`: [`tags`] 标签文件夹
`archive_dir`: [`archives`] 归档文件夹
`category_dir`: [`categories`] 分类文件夹
`code_dir`: [`downloads/code`] `Include code` 文件夹
`i18n_dir`: [`:lang`] 国际化 `i18n` 文件夹
`skip_render`: 跳过指定文件的渲染，您可使用 `glob` 来配置路径。

### 文章

`new_post_name`: [`:title.md`] 新文章的文件名称
`default_layout`: [`post`] 预设布局
`auto_spacing`: [`false`] 在中文和英文之间加入空格
`titlecase`: [`false`] 把标题转换为 title case
`external_link`: [`true`] 在新标签中打开链接
`filename_case`: [`0`] 把文件名称转换为 (1) 小写或 (2) 大写
`render_drafts`: [`false`] 显示草稿
`post_asset_folder`: [`false`] 启动 Asset 文件夹
`relative_link`: [`false`] 把链接改为与根目录的相对位址
`future`: [`true`] 显示未来的文章
`highlight`: 代码块的设置

### 分类 & 标签

`default_category`: [`uncategorized`] 默认分类
`category_map`: 分类别名
`tag_map`: 标签别名

### 日期 / 时间格式

`Hexo` 使用 `Moment.js` 来解析和显示时间。

`date_format`: [`MMM D YYYY`] 日期格式
`time_format`: [`H:mm:ss`] 时间格式

### 分页

`per_page`: [`10`] 每页显示的文章量 (0 = 关闭分页功能)
`pagination_dir`: [`page`] 分页目录

### 扩展

`theme`: 当前主题名称
`deploy`: 部署

## 命令

### 命令简写

``` bash
# 新建
hexo n <title>
hexo new <title>

# 草稿
hexo p <title>
hexo publist <title>

# 生成
hexo g
hexo generate

# 服务器
hexo s
hexo server

# 部署
hexo d
hexo deploy
```

### `init` 初始化

新建一个网站。如果没有设置 `folder` ，`Hexo` 默认在目前的文件夹建立网站。

``` bash
hexo init [folder]
```

### `new` 新建

新建一篇文章。如果没有设置 `layout` 的话，默认使用 `_config.yml` 中的 `default_layout` 参数代替。如果标题包含空格的话，请使用引号括起来。

``` bash
hexo new [layout] <title>
```

** 布局[layout] **

您可以在命令中指定文章的布局(layout)，默认为 `post`，可以通过修改 `_config.yml` 中的 `default_layout` 参数来指定默认布局。

`Hexo` 有三种默认布局：`post`、`page` 和 `draft`，它们分别对应不同的路径，而您自定义的其他布局和 `post` 相同，都将储存到 `source/_posts` 文件夹。

`page`: `source/_posts`
`post`: `source`
`draft`: `source/_drafts`

### `generate` 生成静态文件

生成静态文件。

``` bash
hexo generate
```

`-d`, `--deploy` 文件生成后立即部署网站
`-w`, `--watch` 监视文件变动

``` bash
# 生成静态文件并部署/或者部署前生成静态文件(两条命令相同)
hexo generate -d
hexo deploy -g

# 监视文件变动
hexo generate -w
```

### `publish` 发布草稿

发表草稿。

``` bash
hexo publish [layout] <filename>
```

### `server` 本地服务器

启动服务器。

``` bash
hexo server
```

`-p`, `--port` 重设端口
`-s`, `--static` 只使用静态文件
`-l`, `--log` 启动日记记录，或覆盖记录格式

``` bash
# 重设端口
hexo server -p 5000

# 静态模式
hexo server -s

# 自定义IP
hexo server -i 192.168.1.1
```

### `deploy` 部署

部署网站。

``` bash
hexo deploy
```

`-g`, `--generate` 部署网站前，需要预先生成静态文件

``` bash
# 生成静态文件并部署/或者部署前生成静态文件(两条命令相同)
hexo deploy -g
hexo generate -d
```

### `render` 渲染文件

渲染文件。

``` bash
hexo render <file> ...
```

`-o`, `--output` 设置输出路径

### `clean` 清除缓存

清除缓存文件(`db.json`)和已生成的静态文件(`public`)。

``` bash
hexo clean
```

### `list` 清除缓存

列出网站信息。

``` bash
hexo list <type>
```

`page`, `post`, `route`, `tag`, `category`

### `version` 显示版本

显示 Hexo 版本。

``` bash
hexo version
```

### `migrate` 迁移

从其他系统 [迁移内容]

``` bash
hexo migrate <type>
```

### 选项

#### 安全模式

在安全模式下，不会载入插件和脚本。当您在安装新插件遭遇问题时，可以尝试以安全模式重新执行。

``` bash
hexo --safe
```

#### 调试模式

在终端中显示调试信息并记录到 debug.log。

``` bash
hexo --debug
```

#### 简洁模式

隐藏终端信息。

``` bash
hexo --silent
```

#### 自定义配置文件的路径

自定义配置文件的路径，执行后将不再使用 `_config.yml`。

``` bash
hexo --config custom.yml
```

#### 显示草稿

显示 `source/_drafts` 文件夹中的草稿文章。

``` bash
hexo --draft
```

#### 自定义 CWD

自定义当前工作目录(`Current working directory`)的路径。

``` bash
hexo --cwd /path/to/cwd
```
