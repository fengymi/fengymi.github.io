---
title: hexo-study
date: 2016-10-01 11:37:18
tags: [hexo]
---

[官方文档](https://hexo.io/zh-cn/docs/)

基础工作需要安装node.js 和 git
1.安装一些其他的hexo功能
```
    npm install
    npm install -g hexo-cli	#安装hexo
    npm install hexo --save
    npm install hexo-server # 安装hexo server(发布本地)的功能
    npm install hexo-deployer-git --save # 安装hexo d (使用git提交的功能,需要支持ssh连接github) 
```
<br /> 

<!--more-->
2.常用命令 \[ \](可选) <>(必选)
```
    hexo init [dir] # 将当前[某个]文件夹初始化为hexo目录
    #新建一篇文章。如果没有设置 layout 的话，默认使用 _config.yml 中的 default_layout 参数代替。如果标题包含空格的话，请使用引号括起来。
    hexo new [layout] <title>  
    hexo g # 生成文章
    hexo d # 发布文章到远程仓库

```

3.源码分支
    clone 源码分支，用hexo d 发布源码