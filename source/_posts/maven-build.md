---
title: idea构建maven速度很慢
date: 2016-10-08 14:41:01
tags: [maven,build]
---

加载archetype-catalog.xml文件很慢导致
使用本地archetype-catalog.xml文件即可解决该问题

官网下载： [archetype-catalog.xml](http://repo1.maven.org/maven2/archetype-catalog.xml)
百度云下载： [archetype-catalog.xml](https://pan.baidu.com/s/1eSE4KH8)

1. 下载archetype-catalog.xml文件，并放到.m2/repository/maven/org/apache/maven/archetype/archetype-catalog/2.4/文件夹中
2. 配置idea maven启动方式加 -DarchetypeCatalog=internal
    file->other settings->default settings,搜索maven，再找到 maven-> Runner -> VM Options
    
    
![具体操作](/img/idea/maven-setting.jpg)
