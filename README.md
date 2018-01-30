# git 指令
--------------------------

## 配置

> `git config --global user.name "<user-name>"`

`user-name`: **github 账号**

> `git config --global user.email "<user-emailaddress>"`

`user-emailaddress` : **注册 github 的邮箱**

## 配置秘钥 ssh-keygen

> 生成秘钥:

`ssh-keygen -t rsa -C "<user-emailaddress>"`

> 测试秘钥是否成功

`ssh-T git@github.com`

## 配置ignore文件

> 仓库根目录下

* 创建 `.gitignore` 文件

> 忽略`add`进暂存区的文件/文件件格式

* `/文件夹名/`或`/文件名/`
	
> 不忽略某个文件夹/文件

* `!/文件夹/`或`!/文件/`

## 常用指令
* `git init` 初始化仓库
* `git status` 获取状态
* `ls -ah` 显示隐藏文件
* `git add file` 文件名和后缀名都要写
* `git add .` 添加全部文件/文件夹
* `git commit -m "提交说明"` 提交文件
* `git remote add origin git@github.com:<user-name>/<project-name>.git` 关联自己`GitHub`上的`origin`远程库的仓库
* `git push -u origin master` 推送文件到`github`上的`origin`远程库
* `git push origin master` 推送文件到远程库`origin`的`master`分支

* `git fetch origin master` 从远程仓库`origin`中的`master`分支获取最新版本到本地
* `git merge origin/master` 把远程`origin`下载下来的代码合并到本地仓库

* `git pull origin master` 等价于`git fetch`+`git merge`
* `git clone git@github.com:<user-name>/<project-name>.git` 克隆仓库

## 删除本地仓库
* `find . -name ".git" | xargs rm -Rf`
**即删除本地仓库中的.git文件夹**

## 分支
* `git branch` 查看分支
* `git branch <branch-name>` 创建分支
* `git checkout <branch-name>` 切换分支
* `git checkout -b <branch-name>` 创建并切换至该分支
* `git merge <branch-name>` 合并分支到当前分支
* `git merge --no-ff -m "<commit-message>" <branch-name>` 合并分支,并添加`commit`信息
* `git branch -d <branch-name>` 删除分支
* `git branch -D <branch-name>` 强行删除分支
* `git log --graph` 查看分支合并情况
* `git log --graph --pretty=oneline --abbrev-commit` 查看分支合并情况
* `git checkout -b <branch-name> <response-name>/<branch-name>` 创建远程<response-name>库的<branch-name>分支到本地
* `git branch --set-upstream <branch-name> origin/<branch-name>` 建立本地分支和远程分支的链接

## 工作区
* `git status` 查看工作区
* `git stash` 储存工作区
* `git stash list` 查看工作区
* `git stash apply` 恢复工作区，但stash内容并不删除
* `git stash drop` 删除stash内容
* `git stash pop` 恢复工作区,同时删除stash内容
## 同时关联Gitee和GitHub
`git remote -v` 查看远程库信息

如果没有关联,则执行下列命令进行关联
* 关联`gitee`上的远程库
`git remote add gitee git@gitee.com:<username-name>/<project-name>.git`

* 关联`github`上的远程库
`git remote add github git@github.com:<username-name>/<project-name>.git` 

## 同时提交至Gitee和GitHub上对应的分支
* `git push github <branch-name>`
* `git push gitee <branch-name>`



