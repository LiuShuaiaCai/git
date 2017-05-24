## git学习总结
* git一般步骤：

	git clone [giturl].'\n'
	git add [.|filename].'\n'
	git commit -m 'notice'.'\n'
	git push -u origin master


* git status 查看提交状态
* git diff [filename] 查看文件的修改内容
* git log [--oneline|--pretty] 查看提交日志
* git返回以前的版本 (reset)
	1、返回上一个版本：git reset --hard HEAD^
	2、返回上100个版本：git reset --hard HEAD~100
<<<<<<< HEAD
	3、根据日志编号返回：git reset --hard [number]

* git checkout -- [filename] 撤销修改


* git 分支
	git branch dev 创建dev分支
	git checkout dev 选择dev分支
	以上两个命令简写为： git checkout -b dev
	

=======
	3、根据日志编号返回：
>>>>>>> 04f45f18b24780a8512d3de32eda053ce51d615b
