

---
title: git usage
date: 2021-08-20 18:07:21
tags: Test
categories: blog1
---
使用git’前必须要做的事情（设置用户信息）

Git config --global user.name” name”随便填

Git congig –global user.email”@sina.cn”随便填

（随意）在根目录 touch ~/.bashrc

然后输入

#用于输出git提交日志

alias git-log='git log --pretty=oneline --all --graph --abbrev-commit'

#用于输出当初目录所有文件及基本信息

alias ll='ls -al'

获取本地仓库：在需要上传的代码文件目录右键git bash

git init//初始化当前目录为一个git仓库

touch file01.txt创建一个文件

git status查看当前状态（工作区查看不到内容）

git add .提交全部内容到暂存区

git commit -m "add file01.txt"提交到仓库

git log查看历史记录

vi file01.txt 修改文件以后按ESC然后按大写ZZ即可保存退出

git reset --hard d7e1865版本回退版本号可通过git-log（配置好的）

git reflog查看所有log

添加文件至忽略列表：先创建touch .gitignore文件

Vi .gitignore（进去后添加*.a）不需要提交的的文件后缀设置成.a

Git branch查看分支

Git branch dev01创建分支

Git checkout dev01切换分支

先在master分支然后git merge dev01合并分支（一般时合并到master）

删除分支git branch -d dev01（D时强制删除）

git remote add origin 地址 https

先将内容合并以下$ git pull --rebase origin master

git push -u origin master可以提交空的

<font style="color:rgb(34, 34, 34);">git pull --rebase origin main 就可以了</font>  
<font style="color:rgb(34, 34, 34);">git config --global init.defaultBranch main 将 Git 默认分支从 master 修改为 main，</font>

git push origin main



git分支从master切换到main

背景

本地当前分支为master，远程仓库为main，且远程仓库与本地仓库有 unrelated histories这样的问题，如远程仓库有README.md但本地没有



steps

git checkout -b main

# Switched to a new branch 'main'

git branch

# * main

#  master

git merge master # 将master分支合并到main上

# Already up to date.

git pull origin main --allow-unrelated-histories # git pull origin main会报错：refusing to merge unrelated histories

git push origin main

完成合并



删除某个分支

在本地建立文件夹

将该分支clone下来

git clone -b      该分支名        地址

git  branch -a      (查看远端分支)

git checkout -b 别的分支

git branch -D  要删除的分支

git push origin  --delete     yao 要删除的分支

完成

最完整的将main作为主分支提交

git init

git checkout -b main

<font style="color:rgb(34, 34, 34);">git config --global init.defaultBranch main</font>

git remote add origin http地址

git add .

git commit -m " "[  
](https://blog.csdn.net/qq_33074497/article/details/80506700)<font style="color:rgb(34, 34, 34);">git pull --rebase origin main</font>

<font style="color:rgb(34, 34, 34);">git push origin main</font>



