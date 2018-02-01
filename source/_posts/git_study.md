---
title: git使用教程
date: 2016-10-07 10:09:45
toc: true
tags: [git,版本控制]
---

[官方文档](https://git-scm.com/doc)

### 1. 快速使用
初始化本地仓库目录（获取远程仓库代码）,修改、提交,并推送到远程仓库
``` bash
    #初始化
    git init #初始化本地目录
    #克隆远程代码
    git clone xxxx.git # 克隆并使用远程项目名称
    git clone xxxx.git study # 克隆并新建本地名称

    #修改
    touch test # 新建文件
    git add test # 把某个文件加入到git管理
    git commit -m "test" # 提交到本地

    #推送至远程仓库
    git remote add origin xxxx.git # 添加远程仓库地址 (如果是克隆远程的就不需要添加)
    git push origin master # 提交到master分支
```
<br />

<!--more-->

### 2. 常用管理命令
#### 2.1. 查看
```bash
#分支
    #查看
    git branch # 查看本地分支
    git branch --remote/-r # 查看远程分支
    git branch -a # 查看所有分支
    git branch --merged # 查看已经合并的分支
    git branch --no-merged # 查看未合并的分支
    git branch -vv # 查看本地分支和远程分支的对应情况
    git log # 查看历史提交信息
    git -v # 查看本地最后一次提交信息
#
```
#### 2.2. 操作
```bash
    git checkout -b new_branch # 创建分支(代码来自当前分支,创建时同时会进行切换)
    # 等效这两条命令
    git branch new_branch
    git checkout new_branch
#
    git branch -u origin/branch [now_branch] #将本地当前[其他]分支映射到远程某个分支
    git checkout another_branch # 切换其它分支
    git checkout -b new_branch origin/new_branch # 新建一个本地分支和远程分支进行对应
    git push origin branch_name # 将某个分支提交到远程 (如果远端服务器没有该分支，将会自动创建)
#
    git pull origin branch_name # 从远程获取 branch_name 分支的代码，并合并
    #等效
    git fetch origin branch_name
    git merge branch_name
#
    git merge another_branch # 合并其它分支
#
    git branch -d branch_name # 删除本地分支
    git branch -D branch_name # 强制删除(当被删除的分支还未被合并，就是已经修改但未被合并)
    git push origin :branch_name # 删除远程分支 加:

#状态
    git status # (加 -s/--short ,输出简短信息)
#文件删除
    rm filename # 先从硬盘上删除文件
    git rm filename # 再从git缓冲区删除 -f 强制删除
```
#### 2.3. 基本命令
```bash
    # help 有三种获取命令帮助的方式
    # 1. git help <verb>
    # 2. git <verb> --help
    # 3. man git-<verb>
    git help config
```
<br />

### 3. 全局配置
```bash
    # git config --global X.x "内容" , ～/.gitconfig 可以查看配置信息
    git config --global push.default "current" # 设置push时的默认分支为当前分支 (提交当前分支可以直接git push)
    git config --global user.name "test" # 设置每次提交是的用户 对ssh方式有效
    git config --global user.email "test@test.com"
```
<br />

### 4. 描述

1. 忽视文件 直接添加.gitignore [详细忽视文件](https://github.com/github/gitignore)
<br />
2. origin： 是一个远程分支的别名 .git/config 文件中可以查看

