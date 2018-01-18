---
title: Git Command
date: 2018-01-18 10:26:18
tags:
---
## 分支有关命令
  
   - 查看分支：git branch
   
   - 创建分支：git branch <name>
   
   - 切换分支：git checkout <name>
   
   - 创建+切换分支：git checkout -b <name>
   
   - 合并某分支到当前分支：git merge <name>
   
   - 删除分支：git branch -d <name>
   * 【git 删除本地分支】
   git branch -D br
   * 【git 删除远程分支】
   git push origin :br  (origin 后面有空格)
   
   
   ## 远程库的详细信息
   想把一个项目开源出去，提交到github上面去，免不了就要切换远程仓库地址。那这时候有什么办法解决呢？
   据目前自己的了解，有三种办法。
   一、修改命令
   git remote set-url origin url
   二、先删后加
   git remote rm origin
   git remote add origin git@github.com:sheng/demo.git
   三、修改config文件
   如果你的项目有加入版本控制，那可以到项目根目录下，查看隐藏文件夹， 发现.git文件夹，找到其中的config文件，就可以修改其中的git remote origin地址了。
   - 显示当前所有远程库的详细信息
     git remote -v
    ## 查看分支差异
	查看 dev 有，而 master 中没有的：                           
	git log dev ^master 
	同理查看 master 中有，而 dev 中没有的内容：
	git log master ^dev

	查看 dev 中比 master 中多提交了哪些内容：

	git log master..dev
	注意，列出来的是两个点后边（此处即dev）多提交的内容。同理，想知道 master 比 dev 多提交了什么：
	git log dev..master