---
title: Hexo + github pages 博客多台机器同步问题
---
### 在博客仓库中新建一个新分支hexo-source 用来存放hexo数据，theme通过submodule管理

    $ cd ryanxci.github.io
    $ git init
    $ git checkout -b hexo-source
    $ git add .
    $ git commit -m "init hexo source"
    $ git remote add origin git@github.com:ryanxci/ryanxci.github.io.git
    $ git submodule add git@github.com/theme-next/hexo-theme-next themes/next
    $ git push origin hexo-source

### 在另一台机器上
    $ git clone git@github.com:ryanxci/ryanxci.github.io.git
    $ cd ryanxci.github.io
    $ git checkout hexo-source
    $ git submodule init
    $ git submodule update
    $ npm install
    $ hexo generate && hexo server
