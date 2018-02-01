---
title: hexo-study
date: 2016-10-01 11:37:18
toc: true
tags: [hexo]
---

[官方文档](https://hexo.io/zh-cn/docs/)

基础工作需要安装node.js 和 git
```
    #配置npm全局安装目录及缓存目录
    npm config set prefix "%NODE_HOME%/node_global"
    npm config set cache "%NODE_HOME%/node_cache"
```

### 1. hexo安装
安装一些其他的hexo功能(项目根目录执行)(使用npm install命令, 安装当前package.json下的依赖)
```
    npm install
    npm install -g hexo-cli	#安装hexo(全局安装)
    npm install hexo --save # 保存到package.json文件(项目根目录)
    npm install hexo-server # 安装hexo server(发布本地)的功能
    npm install hexo-deployer-git --save # 安装hexo d (使用git提交的功能,需要支持ssh连接github) 
```
<br /> 

<!--more-->
### 2. 常用命令
```bash
    # [](可选) <>(必选)
    hexo init [dir] # 将当前[某个]文件夹初始化为hexo目录
    #新建一篇文章。如果没有设置 layout 的话，默认使用 _config.yml 中的 default_layout 参数代替。如果标题包含空格的话，请使用引号括起来。
    hexo new [layout] <title>  
    hexo g # 生成文章
    hexo s # 本地启动
    hexo d # 发布文章到远程仓库(需要配置相应的代码存储仓库)

```