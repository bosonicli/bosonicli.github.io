---
title: 2022-07-10 - 使用 Hexo 部署GitHub Pages.md
date: 2022-07-10 18:55:40
tags:
- Hexo
---
本小白第一天尝鲜 Hexo + GitHub Pages ，折腾半天发现我没搞清楚一个根本性的问题：

那就是 Hexo 部署的网页和 GitHub 仓库托管的源码不是一个东西。

所以跟我一样的小白在折腾之前应该至少给 GitHub 仓库预留两个分支：

+   master

    用于存储博客源码

    GitHub 因为政治正确的原因会将默认分支名字设置成 main ，可能影响与 VSCode 等工具的配合，建议保持默认分支名字为 master

+   gh-pages

    用来部署编译后的静态页面(可以是其他任何名字)

    GitHub Pages 现在可以设置用来部署静态网页的分支。在仓库的 Settings 界面选择 Pages ，将部署的分支设置成这个。

    在 Hexo 的配置文件 `_config.yml` 中，将 Hexo 部署的分支设置成这个：

    ```
    deploy:
        type: git
        repo: https://github.com/<username>/<repository>
        # example, https://github.com/bosonicli/bosonicli.github.io
        branch: gh-pages
    ```

    这样，经 Hexo 编译后的静态页面 HTML 文件就部署到了 gh-pages 分支，然后经由 GitHub Pages 工具就可以自动部署到域名上了