# git 指令
--------------------------


## 配置

	$ git config --global user.name "Your Name"
	$ git config --global user.email "email@example.com"

Your name: **github 账号**

email@example.com : **注册 github 的邮箱**


##配置秘钥 ssh-keygen

> 生成秘钥

	1. $ ssh-keygen -t rsa -C "youremail@example.com"

> 测试秘钥是否成功

	2. ssh-T git@github.com		测试是否成功
	

## 常用指令

	$ git init		初始化仓库
	$ git status 	获取状态
	$ ls -ah		显示隐藏文件
	$ git add file		file和后缀名都要写
	$ git add *		全部添加
	$ git commit -m "提交说明"		提交文件
	$ git remote add origin git@github.com:jessie-zly/-.git		关联自己GitHub上的仓库
	$ git push -u origin master		推送文件到github
	
	$ git push origin master	

	$ git fetch origin master 从远程仓库获取最新版本到本地

	$ git merge origin/master 把远程下载下来的代码合并到本地仓库

	$ git clone git@github.com:账号/仓库名.git



## 删除本地仓库

	 $ find . -name ".git" | xargs rm -Rf

> **即删除本地仓库中的.git文件夹**
	
	


# git使用时出现的问题
------------

	1. $ git push -u origin master
		To github.com:jessie-zly/DevelopSoftware.git
		 ! [rejected]        master -> master (fetch first)
		error: failed to push some refs to 'git@github.com:jessie-zly/DevelopSoftware.git'
		hint: Updates were rejected because the remote contains work that you do
		hint: not have locally. This is usually caused by another repository pushing
		hint: to the same ref. You may want to first integrate the remote changes
		hint: (e.g., 'git pull ...') before pushing again.
		hint: See the 'Note about fast-forwards' in 'git push --help' for details.

原因:

**GitHub远程仓库中的README.md文件不在本地仓库中**

解决方案:

执行
	
	git pull --rebase origin master

再执行

	git push -u origin master