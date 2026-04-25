---
title: Hexo-NexT 特定文章不显示侧边栏
date: 2018-11-14 16:10:47
tags: hexo
categories: skills
---
本文提供了一种方法解决Hexo博客侧边栏自动弹出的问题
<!--more-->
### 问题
NexT 主题的侧边栏可以在`.../themes/next/_config.yml`里修改：
```
# Sidebar Display, available value (only for Muse | Mist):
  #  - post    expand on posts automatically. Default.
  #  - always  expand for all pages automatically
  #  - hide    expand only when click on the sidebar toggle icon.
  #  - remove  Totally remove sidebar including sidebar toggle.
  display: post
  #display: always
  #display: hide
  #display: remove
```
但是这里只能修改所有post的设置，不能对特定文章进行修改。
### 解决方案
[issues-943](https://github.com/iissnan/hexo-theme-next/issues/943)上的解决方法。
在`.../themes/next/layout/_marcro/sidebar.swig`文件中找到下面内容
```
{% set display_toc = is_post and theme.toc.enable or is_page and theme.toc.enable %}
```
将其修改为
```
{% set display_toc = is_post and theme.toc.enable and !page.no_toc or is_page and theme.toc.enable and !page.no_toc %}
```
然后只需要在你不想显示目录的文章头部属性增加：`no_toc: true`即可