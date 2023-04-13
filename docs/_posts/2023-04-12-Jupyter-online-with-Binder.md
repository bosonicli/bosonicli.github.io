---
title: Jupyter online with Binder
date: 2023-04-12
author: bosonicli
tags:
-   MehrWert
---

# Intro

[The Binder project][Binder] is an integration project to share computing environments to everyone.

If you want to share a computing environment hosted in a [Github][Github] public repository, the easiest way is to use the [myBinder][myBinder] deployment as follows:

1.  Assign your config to `environment.yml` file in your repository, for eg

    ```bash
    name: env-name
    channels:
      - conda-forge
    dependencies:
      - python=3.X
      - pip
      - pip:
        - numpy
        - pandas
        - matplotlib
        - scipy
        - jupyter
    ```

2.  Visit [myBinder][myBinder].

    Fill in your repository URL, branch, and path to `.ipynb` file (optional)

    >   https://github.com/name-account/name-repo
    >
    >   name-branch
    >
    >   path-to-nb/name-nb.ipynb

    If a `.ipynb` is specified, myBinder will launch an interactive environment of this notebook, else an environment of the whole branch

3.  Press `launch`, myBinder will check `environment.yml` file, config a corresponding env, build an image of your repo/nb, and open this image in a new page.

    You can then run and interact with these notebooks in the image

4.  This image of your repo/nb can be accessed through a Binder URL like

    >   https://mybinder.org/v2/gh/name-account/name-repo/name-branch?labpath=path-to-nb%2Fname-nb.ipynb

    or with no nb specified

    >   https://mybinder.org/v2/gh/name-account/name-repo/name-branch

    You can then share it to others and they can access your repo/nb through this URL

5.  Everytime this URL is accessed, myBinder will build an image of your repo/nb. If it has been built before and no new change happens, it will skip the building and call the former image to save time. 

    So please do launch myBinder everytime you make new changes to your repo


# Appendix

[Github]:https://github.com

[Binder]:https://jupyter.org/binder

[myBinder]:https://mybinder.org/