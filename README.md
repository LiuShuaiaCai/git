## git学习总结
* git 教程
	易百教程：http://www.yiibai.com/git/git_pull.html
	廖雪峰的官方网站：http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137602359178794d966923e5c4134bc8bf98dfb03aea3000
* git一般步骤：

	git clone [giturl]
	git add [.|filename]
	git commit -m 'notice'
	git push -u origin master


* git status 查看提交状态
* git diff [filename] 查看文件的修改内容
* git log [--oneline|--pretty] 查看提交日志
  git log --graph --pretty=oneline -abbrev-commit
* git返回以前的版本 (reset)
	1、返回上一个版本：git reset --hard HEAD^
	2、返回上100个版本：git reset --hard HEAD~100
	3、根据日志编号返回：git reset --hard [number]

* git checkout -- [filename] 撤销修改


* git 分支
	git branch dev 创建dev分支
	git checkout dev 选择dev分支
	以上两个命令简写为： git checkout -b dev
	
	git merge dev 合并dev分支
	git branch -d dev 删除分支

	注意：先提交到dev,在切换到master，然后执行merge，进行commit，最后push

* git 修复BUG
	+ 存储当前场景：git stash
	+ 查看场景列表：git stash list
	+ 恢复场景：git stash replay
	+ 删除场景：git stash drop
	+ 恢复、删除：git stash pop 

===========================================================================
分支：
线上：master
测试：beta
dev

git merge 合并分支
study hard
