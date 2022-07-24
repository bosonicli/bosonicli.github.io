---
title: 2022-07-10 - 使用 Hexo 部署GitHub Pages.md
date: 2022-07-10 18:55:40
tags:
- Blog
---
本小白第一天尝鲜用 Hexo + GitHub Pages 部署个人博客 ，浪费了一天踩各种坑，记录一下经验教训。

首先，我想要做什么？为什么用 Hexo + GitHub Pages ？

我希望拥有

1.  一套便捷好用的 Markdown to HTML 静态网页渲染工具

2.  一个便捷好用的静态网页托管平台

3.  一个好用的源码托管平台

这样我可以用 Markdown 在本地记一些日常笔记，实时同步到源码托管平台，随时把笔记渲染成静态网页，随时推送到网页托管平台展示给外界看。如此，我的本地笔记本就变成一个开放博客，既方便多端编辑，方便随时展示，也方便迁移。

GitHub Pages 提供了一套网页托管服务，可以把仓库内的 HTML 静态网页自动推送到域名上。这样一个 GitHub 仓库就可以同时扮演 2/3 两个角色。Hexo 是一个好用的渲染工具，因此我选择了这两个的组合。

这个方案就是我踩坑一整天的原因：源码托管和网页托管是 **两个不同的功能** ，我想用同一个 GitHub 仓库来实现，不是不行，但搞不好就会导致混乱。相关工具/教程 (如 Hexo) 也并不默认两个功能用同一个仓库实现，使用时也要注意。

方便的做法是，将这个同时托管源码和静态网页的 GitHub 仓库，至少区分两个分支：

1.  master(不建议用其他分支名)

    博客源码分支(如 Markdown)，编辑区

    建议保持默认分支名字为 master ，以免影响与 VSCode 等工具的配合

1.  gh-pages(或其他分支名)

    静态网页分支，非编辑区

    GitHub Pages 现在可以选择用来部署静态网页的分支。在仓库的 Settings 界面选择 Pages ，将部署的分支设置成这个。

    在 Hexo 的配置文件 `_config.yml` 中，将 Hexo 部署的分支也设置成这个：

    ```
    deploy:
        type: git
        repo: https://github.com/<username>/<repository>
        # example, https://github.com/bosonicli/bosonicli.github.io
        branch: gh-pages
    ```

    这样，Hexo 会将源码渲染为 HTML 静态页面，自动部署到仓库的 gh-pages 分支。然后 GitHub Pages 工具自动抓取这个分支的静态页面，就可以自动部署到域名上了。

之后如需迁移博客，只需迁移源码分支 master ，之后重新部署渲染工具 Hexo 即可。

这也是我想尝试个人博客的初衷，博客应当是轻便的。把渲染后的HTML一并迁移走略显累赘。

遇到其他的需求(比如用 GitBook 写操作文档)这套方案就并不适用，不过等我需要用的时候再寻求新方案不迟。

## 参考文献

搞清楚上面的问题参考了[这篇博客](https://segmentfault.com/a/1190000017366905)
