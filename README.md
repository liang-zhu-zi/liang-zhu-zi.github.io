# liang-zhu-zi.github.io

<https://liang-zhu-zi.github.io>

## Setup Project

[Instructions](https://jekyllrb.com/docs/#instructions)

```bash
# Check your Jekyll version
jekyll -v
# jekyll 4.2.2

# install the jekyll and bundler gems.
gem install jekyll bundler

# Create a new Jekyll site
jekyll new liang-zhu-zi.github.io
cd liang-zhu-zi.github.io

# If you are using Ruby version 3.0.0 or higher, step 5 may fail. You may fix it by adding webrick to your dependencies:
bundle add webrick

# Build the site and make it available on a local server.
bundle exec jekyll serve

# Browse to http://localhost:4000
```

以下内容转自 <https://tianqi.name/jekyll-TeXt-theme/docs/zh/quick-start>

## 添加主题

1. 将 `jekyll-text-theme` 主题添加到您站点的 *Gemfile* 文件中：

   ```ruby
   gem "jekyll-text-theme"
   ```

2. 向站点的 *_config.yml* 中加入下列代码来启用主题：

   ```yaml
   theme: jekyll-text-theme
   ```

## 设置

Jekyll 主题含有主题默认的布局文件、包含文件和样式表， 但是有些目录（例如*assets*, *_layouts*, *_includes* 以及 *_sass* 目录）需要手动添加到项目目录中，这样的好处在于将主题的文件和站点的内容和配置隔离开来，方便主题的升级。

```bash
├── 404.html
├── Gemfile
├── _config.yml
├── _data
│   └── locale.yml
├── _posts
│   └── ...
├── about.md
├── archive.html
└── index.html
```

- `Gemfile` 须手动合并。
- `index.markdown`, `about.markdown`, `_posts\2022-05-15-welcome-tojekyll.markdown` 没有使用，请删除。


你可以参考主题源码的 [/test 目录](https://github.com/kitian616/jekyll-TeXt-theme/tree/master/test), 这是一个使用主题的示例。

## 安装开发环境

如果你想本地运行主题，你需要安装 Ruby 以及 Jekyll，详情请戳 [这里](https://jekyllrb.com/docs/installation/)。

上述步骤完成后，安装 Ruby 依赖包：

```bash
bundle install --path vendor/bundle
```

`Run bundle info --path` followed by the name of the theme’s gem, e.g., `bundle info --path jekyll-text-theme` for Jekyll’s default theme.

This returns the location of the gem-based theme files. For example, the Minima theme’s files might be located in `<your_project_path>/vendor/bundle/ruby/3.1.0/gems/jekyll-text-theme-2.2.6` on Windows 10.


## 本地预览

Jekyll 集成了一个开发用的服务器，可以让你使用浏览器在本地进行预览。

通过 `bundle exec jekyll serve` 命令启动开发服务器，然后你就可以访问 [http://localhost:4000/](http://localhost:4000/) 预览你的网站了。

如果是通过 Docker 搭建的环境，请运行 `docker-compose -f ./docker/docker-compose.default.yml up` 命令以启动开发服务器。

## 编译和发布

如果你打算把网站搭建在 GitHub Pages 上，那你所需要做的就是将项目的源码上传到 USERNAME.github.io 源码仓库的 master 分支，GitHub 会自动的编译，几分钟后你就可以通过 **https://USERNAME.github.io** 访问到你的网站了。

如果你的网站是搭建在其他服务器上的，那么你就需要来自己编译了。首先运行命令 `JEKYLL_ENV=production bundle exec jekyll build` 编译你的网站，然后将编译的文件（位于 *_site* 目录）更新到你的服务器上。
