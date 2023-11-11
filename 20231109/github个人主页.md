# github个人主页

Jekyll是一个简单的，博客感知的静态站点生成器。

你将内容创建为文本文件（Markdown），并将其放到到文件夹中。然后，使用Liquid-enhanced HTML模板构建网站。Jekyll自动将内容和模板联系在一起，生成完全由静态资源组成的网站，它适合上传到任何服务器。

Jekyll恰好是GitHub Pages的引擎，因此你可以在GitHub的服务器上免费托管项目的Jekyll页面/博客/网站。


- **Ruby**：
Ruby 是一种高级、解释型的编程语言，以其面向对象、灵活和易于使用的特性而闻名。它被广泛用于 Web 开发、自动化脚本、数据处理等领域。

- **Gems**：
在 Ruby 世界中，一个 "gem" 是一个库或应用程序的包装，它包含了代码、文档和相关的信息。RubyGems 是 Ruby 的一个包管理器，它提供了一个标准化的格式来分发 Ruby 程序和库（即 gem），以及一个管理这些安装 gem 的工具。

- **Gem**：
单数形式的 "gem" 指的是一个具体的 Ruby 库或应用程序，这些都可以通过 RubyGems 来安装和管理。例如，Rails、RSpec、Nokogiri 都是流行的 Ruby gems。

- **Bundler**：
Bundler 是一个用于 Ruby 项目的依赖管理工具。它允许您指定一个项目所依赖的 gem，并确保这些依赖在所有环境中一致。它使用一个名为 Gemfile 的文件来跟踪一个项目的依赖，并通过 Gemfile.lock 来锁定这些依赖的具体版本。

- **Jekyll**：
Jekyll 是一个静态网站生成器，它使用 Ruby 编写。它通过处理 Markdown、HTML 文件等内容，转换成静态网页。Jekyll 本身也是一个 gem，可以通过 RubyGems 安装。


## 1 环境安装

1. 安装 ruby

```sh
sudo apt-get install -y ruby-full build-essential zlib1g-dev
```

2. 添加环境变量

```sh
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

<span style="background-color: pink">不进行环境变量设置可能会有以下问题：

![Alt text](<./image/Screenshot from 2023-11-09 18-18-48.png>)

3. 安装 Bundler （也就是安装ruby开发的库或者应用程序）

```sh
# 通过RubyGems安装Jekyll和Bundler gems
gem install jekyll bundler
# 使用github-pages
gem install github-pages
```

安装成功

![Alt text](<./image/Screenshot from 2023-11-10 16-25-04.png>)

## 2 本地构建

桌面上新建一个静态网站项目

```sh
# 在./my-blog创建一个新的Jekyll站点
jekyll new my-blog
```

接下来，导航到网站文件夹。你会注意到一个基本的Jekyll网站结构，包括像这样的目录和文件：

![Alt text](<./image/Screenshot from 2023-11-11 15-19-37.png>)

```sh
# 在本地预览服务中编译站点
bundle exec jekyll serve

# 浏览器里面打开 http://localhost:4000
```

### 2.1 关于Bundler

gem install bundler命令将通过RubyGems安装bundler gem。你只需要安装一次即可——不用每次创建一个Jekyll项目的时候都安装一次。这里有一些额外的细节：


- bundler是一个管理其他Ruby gems的gem。它确保你的gems和gem版本兼容，并且确保包含每个gem需要的必须依赖。


- Gemfile和Gemfile.lock文件将告知Bundler有关于你的站点中的gem依赖。如果你的站点没有这些Gemfile文件，则可以省略 `bundle exec` 命令，直接运行 `jekyll serve` 命令。


- 当你运行 `bundle exec jekyll serve` 时，Bundler使用Gemfile.lock中指定的gem和版本来确保你的Jekyll站点没有兼容性或依赖冲突。

### 2.2 使用Jekyll创建一个新的站点选项

`jekyll new <PATH>` 在指定的路径（相对于当前目录）安装一个新的Jekyll站点。 在上面列出的命令行的情况下，Jekyll将被安装在当前目录下的名为 `myblog` 的目录中。这里有一些额外的细节：


- 要将Jekyll站点安装到你当前所在的目录中，请运行 `jekyll new .` 。 如果现有的目录不是空的，你可以使用 `jekyll new . --force` 传递- -force 选项。


- `jekyll new` 会自动启动 `bundle install` 以安装所需的依赖关系。 （如果你不想让Bundler安装gem，请使用jekyll new myblog --skip-bundle。）


- 默认情况下，由 `jekyll new` 安装的Jekyll站点使用一个叫做为Minima的基于gem的主题。使用基于gem的主题，一些目录和文件存储在gem主题中，隐藏在你的即时视图中。


- 我们建议你将Jekyll设置为基于gem的主题，但如果你想从空白的模版开始，请使用 `jekyll new myblog --blank` 。


- 要了解其他参数，你可以使用 `jekyll new` ，输入` jekyll new --help` 即可。

> 如果有疑问，请使用help命令来提示你所有可用的选项和用法，它也适用于 new 和 build 以及 serve 命令，例如，`jekyll help new` 或 `jekyll help build`。

### 2.3 基本用法

Jekyll gem在终端窗口中为你提供了一个 `jekyll` 可执行文件。你可以通过多种方式使用此命令：

```sh
jekyll build
# => 当前文件夹中的内容将被生成到./_site

jekyll build --destination <destination>
# => 当前文件夹中的内容将被生成到<destination>

jekyll build --source <source> --destination <destination>
# => <source>文件夹中的内容将被生成到<destination>

jekyll build --watch
# => 当前文件夹中的内容将被生成到./_site,
#    检查改动，并自动重新生成。
```

### 2.4 重写默认开发配置

