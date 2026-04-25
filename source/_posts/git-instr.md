---
title: Git常用命令
date: 2020-02-28 12:42:10
tags:
  - git
categories: skills
---
常用？不常用？
<!--more-->
# Git 常用命令
### 查看用户名和邮箱

```bash
git config user.name
git config user.email
```

### 修改用户名和邮箱

```bash
git config --global user.name "username"
git config --global user.email "user@email.com"
```

### 设置代理

在本地开启代理后执行下列命令（小飞机用sock5协议）

```bash
git config --global http.proxy http://127.0.0.1:1080
git config --global https.proxy https://127.0.0.1:1080
git config --global http.proxy 'socks5://127.0.0.1:1080' 
git config --global https.proxy 'socks5://127.0.0.1:1080'
```

### 取消代理

```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```

### 查看分支

```bash
git branch "branchname"
git branch -a "remote_branchname"
```

### 切换/添加新分支

```bash
git checkout "branchname"
git checkout -b "new_branchname"
```
