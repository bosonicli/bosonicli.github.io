---
title: 2022-12-20 - 使用Jekyll 在 GitHub-Pages 上部署博客
date: 2022-12-20
author: bosonicli
tags:
-   Blog
---

# 转战 jekyll

如同我在之前的

[使用Hexo在Github-Pages上部署博客][2022-07-10-Hexo]

这篇博客中所说，我希望拥有这样一套工具来配置我的个人博客：

1.  一套便捷好用的 文本 转 网页 的工具，能方便地显示公式/代码、组织链接/标签；

2.  一个便捷好用的静态网页托管平台；

3.  一个好用的文本源码托管平台。

这样我就可以实现把个人博客站点当本地笔记一样使用。有想写的东西就在本地目录随便写点，写完后简单操作几步就能发布到博客上。

操作要尽可能简便和傻瓜化，这样既能帮助我每次写东西只专注于内容上而不会在形式上过于折腾，又能保持博客本身尽可能简约，方便适配其他工具或平台。

最初选用 [Hexo][Hexo] 作为工具时，看中的是 [Github-Pages][Github-Pages] 能同时扮演2/3 两个角色。但美中不足，Hexo的文本转网页渲染和托管部署还得分开两步来做，这也是我折腾好半天的原因。

因此稍加思考我还是转向了 [jekyll][jekyll] 这款工具。Github-Pages 内置jekyll 渲染引擎，1/2/3功能完全整合到了一起。我要做的只是以 `.md` 形式专心写内容，然后同步上传到 [Github][Github] 仓库，仓库会自动替我渲染、发布。这已经基本是我理想中的个人博客工具了。

可惜 jekyll 对 Latex 公式的默认支持不顺畅，直接导致我希望通过博客传达的内容被阉割了一半，直到今天我才解决掉这个很基本的小问题，博客才终于能正常运行了。

# 配置 jekyll

为了专注于内容，我用的 jekyll 主题是 [minima][minima] ，这也是按照 jekyll 教程初始化站点目录时自动适用的主题。

想要正常使用一个名为 "theme-name" 的主题，需要在 `_config.yml` 配置文件里添加

``` bash
theme: theme-name
```

并在 `Gemfile` 里添加

``` bash
gem "theme-name"
```

每次更改主题或页面配置后，运行

``` bash
bundle install
```

以刷新配置

博客写好后，可运行渲染命令

``` bash
bundle exec jekyll serve
```

然后浏览器打开 `http://127.0.0.1:4000/` 来本地预览渲染后的网页效果

同样的渲染命令在提交博客内容至 Github 仓库后会由 Github-Pages 内置的引擎自动运行

渲染命令会按照主题指定的样式 (通常是 `.css` 文件) 和页面设置，将 `.md` 文本渲染为静态页面 `.html`

主题的页面设置，以 `page-type.html` 文件的形式存在，一般在主题目录的 `_layouts/` 目录下。在博文/博客页面的文本文件 `.md` 头部，设置

``` bash
---
layout: page-type
---
```

来让 jekyll 用 `page-type.html` 文件制定的页面设置渲染 `.md` 文件的内容

如果博客站点目录下的 `_layouts/` 目录里有同名文件，则优先适用这些文件的设置，即站点目录>主题目录。

更换主题时就会遇到这个问题：不同主题对博文/博客页面的渲染设置，甚至页面的组织方式都有区别。如 minima 主题，是指定以 `_layouts/home.html` 文件的样式来渲染站点目录下的 `index.md` 文件，以生成站点的首页和目录。更换其他主题时，如 jekyll-theme-minimal ，只更改 `Gemfile` 和 `_config.yml` 文件的相关设置是无效的，正确做法是把整个站点目录都用新主题相同方式组织。否则会出现这样的情况：原主题 minima 的页面文件 `index.md` 指定使用 `_layouts/home.html` 的页面设置，而新主题 jekyll-theme-minimal 目录下却没有这个页面设置文件，因此首页渲染会失败，你只能得到一个打不开任何内容的博客站点。

所以，需要更换主题时稳妥的做法是，将所有博文文档 `.md` 备份到合适的地方，把新主题的目录 fork 下来覆盖本地的站点目录，重新初始化，然后再把博文文档拷贝回 `_posts/` 目录里。

这么折腾显然违背了我“想随手写点东西”的宗旨，因此我最终还是没有改更好看的主题，用回了默认的 minima ，反正对于我显示公式/代码的需求也够用了。

之前一直没折腾博客就是因为公式无法正常显示。因为 minima 默认的页面设置 `_layouts/post.html` 里没有指定 Latex 渲染引擎。为了解决这个问题，我从 minima 主题目录里拷出 `_layouts/post.html` 放在了站点目录下，然后按照 [这篇博客][Librarius-MathJax] 的指导，添加了一段代码进 `<headers>` :

```bash
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
```

公式就能正常显示了。

所以想要博客显示随自己心意，还是得在站点目录下设置自己的 `_layouts/page-type.html` 页面设置文件。好在如果不想折腾，这些文件也只需要配置一次。之后就可以专注于写内容本身了。

我就不说什么“坚持写博客”了。随手写两笔本就应当是一个习惯成自然的事情，就好比坚持运动的目的应当是有一天运动就像吃饭喝水一般内化成了日常生活的一部分。现在博客配置好了，希望今后随手写两笔也能像吃饭喝水一样自然吧。

# Ref

[Github]:https://github.com

[Github-Pages]:https://pages.github.com

[jekyll]:https://jekyll.com.cn

[Hexo]:https://hexo.io/zh-cn

[minima]:https://github.com/jekyll/minima

[Librarius-MathJax]:https://lloyar.github.io/2018/10/08/mathjax-in-jekyll.html

[2022-07-10-Hexo]:(2022-07-10-使用Hexo在GitHub-Pages上部署博客.md)
