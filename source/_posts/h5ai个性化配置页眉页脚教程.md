---
title: h5ai个性化配置页眉页脚教程
date: 2018-05-25 15:02:47
tags:
    - h5ai
    - html 
categories: skills
---
近日h5ai配置已接近完成，在配置插件时发现h5ai支持自定义header和footer，但doc中却并没有写清楚，终于[@Supreme-Liam](https://blog.lipf.tech/)解决了这个问题，便将solution转载到小站以便参阅。
<!--more-->
# 什么是 h5ai

h5ai是一款功能强大 php 文件目录列表程序，由德国开发者 Lars Jung 主导开发，它提供多种文件目录列表呈现方式，支持多种主流 Web 服务器，例如 Nginx、Apache、Cherokee、Lighttpd 等，支持多国语言，可以使用本程序在线预览文本、图片、音频、视频等。

本教程适用于已配置h5ai的同学，如需了解更多，详情点击官网：[https://larsjung.de/h5ai/](https://larsjung.de/h5ai/)

# h5ai页眉页脚设置

h5ai作者在主配置文件`_h5ai/private/conf/options.json`提到，

```
/*
  Allow customized header and footer files.
  First checks for files "_h5ai.header.html" and "_h5ai.footer.html" in the current directory.
  If not successful it checks all parent directories (starting in the current directory) for
  files "_h5ai.headers.html" and "_h5ai.footers.html".
  Note the different filenames: "header" (only current) - "headers" (current and sub directories)!
  The file's content will be placed inside a <div/> tag above/below the main content.
  If a file's extension is ".md" instead of ".html" its content will be interpreted as markdown.
*/
"custom": {
"enabled": true
},
```

由此可见，想要为h5ai添加页眉和页脚，只需要在对应目录下放置好`_h5ai.header.html`或`_h5ai.footer.html`，同时h5ai自身支持Markdown格式页面，同样可以作为页眉页脚插入网页。

需要注意的是，不同文件名称以及不同的存放位置会呈现不同的效果。

## 子文件夹内的_h5ai.header.html与_h5ai.footer.html

通过配置文件可知，此种页眉页脚仅在访问该目录时才会显现

```
├── _h5ai
│   ├── private
│   └── public
│   └── .htaccess
├── my music
│   ├── test.mp3
│   ├── sing.mp3
│   ├── record.mp3
│   └── _h5ai.header.html
├── my video
│   ├── video.mp4
│   ├── record.mp4
│   └── _h5ai.footer.html
```

如上存储目录所示，仅在访问`my music`文件夹时，加载该目录下的`_h5ai.header.html`

类似地，仅在访问`my video`文件夹时，加载该目录下的`_h5ai.footer.html`

# 根目录下的_h5ai.headers.html与_h5ai.footers.html

通过配置文件可知，此种页眉页脚在访问根目录时呈现并传递（反继承？？）给其所有子目录

```
├── _h5ai
│   ├── private
│   └── public
│   └── .htaccess
├── my music
│   ├── test.mp3
│   ├── sing.mp3
│   └── record.mp3
├── my video
│   ├── new
│   │    ├── new.mp4
│   ├── video.mp4
│   ├── record.mp4 
│   └── _h5ai.footers.html
└── _h5ai.headers.html
```

如上存储目录所示

在访问`my music`和`my video`文件夹时，加载根目录下的`_h5ai.headers.html`，即在两个目录下显示出的页眉与访问根目录的页眉相同

在访问`my video\new`文件夹时，加载`my video`下的`_h5ai.footers.html`，即在`my video\new`目录下显示出的页眉与访问`my video`目录的页眉相同

# 结束语

相信通过以上的说明，你已经了解了如何个性化配置h5ai的页眉与页脚

更多关于h5ai配置的文章请移步 [尚未完工]

转载来源：[https://blog.lipf.tech/106/h5ai个性化配置页眉页脚教程/](https://blog.lipf.tech/106/h5ai个性化配置页眉页脚教程/)
