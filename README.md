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

* 删除远程分支  
    + git branch -r -d origin/branch-name  
    + git push origin :branch-name  


* 要删除服务器远端的分支，则执行如下所示的命令：
	+ git push origin –delete 分支名

* 如果是要删除本地已经合并了的分支，则执行：
	+ git branch –d 分支名
* 下图中的命令是为了删除本地未合并的分支：
 	+ git branch –D 分支名

===========================================================================
分支：
线上：master
测试：beta
dev

git merge 合并分支
study hard


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
## 项目迭代过程：
* 创建新的分支，在新的分支上开发本次的迭代
	
	git checkout -b feature/20170620_lsc_XXX

* 开发完成，上传测试环境，通知测试人员测试
	
	+ 获取新的代码 
		git pull origin feature/20170620_lsc_XXX
	+ 把本次修改内容添加到暂存区
		git add -A
	+ 把暂存区内容提交到版本库
		git commit -am 'update'
	+ 把本次的修改推送到远程仓库
		git push origin feature/20170620_lsc_XXX

* 上传beta环境：每次迭代都会新建一个公共分支 feature/20170620_ielts_common
	
	+ 获取（fetch）远程的公共分支（feature/20170620_ielts_common）
		git fetch origin feature/20170620_ielts_common:feature/20170620_ielts_common
	+ 在公共分支（feature/20170620_ielts_common）中合并本次迭代分支（feature/20170620_lsc_XXX）
		- 拉取代码
		git pull origin 20170620_ielts_common
		- 合并分支
		git merge feature/20170620_lsc_XXX
	+ 把合并后的公共分支（feature/20170620_ielts_common）推送到远程
		git status -sb
		git push origin feature/20170620_ielts_common

* 解决冲突
	
	+ 切换到dev分支
		git checkout dev
	+ 拉取远程的代码
		git pull
	+ 合并当前修改的分支（feature/20170620_lsc_XXX）
		git merge feature/20170620_lsc_XXX
	+ 解决冲突
	+ 把修改后的dev推送远程
		git push

