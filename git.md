##git指令  

###基本使用

* 配置git  
`git config --global user.name "用户名"` 用户名标识当前电脑  
`git config --global user.email "邮箱"`  
`git config -l` 查看本地git的所有配置信息  

* 生成ssh  
`ssh-keygen -t rsa -C 邮箱`  
ssh秘钥保存在id_rsa.pub文件中  
`ssh -T git@github.com`  
查看电脑是否能链接到版本控制网站

* 关联远程仓库  
`git remote add origin 远程仓库地址`将本地仓库与远程仓库关联  
`git remote -v`查看当前仓库的现有的远程关联  
`git remote rm origin`删除现有的远程关联  
关联后，第一次提交用`git push -u origin master`指令（参数-u） 

* 查询指令  
`git --version` 查询git的版本号

* `git init` 初始化一个git仓库  
* `git add ./` 将当前**工作区**目录下的所有文件和目录提交到**暂存区**  
* `git commit -m "备注"`将暂存区的文件提交到**版本库**  
* `git push origin branch`将当前分支的所有提交全部同步到远程分支*branch*上  
* `git checkout -b branch`创建*branch*分支，并切换到*branch*分支上  
* `git checkout branch`切换到*branch*分支上  
* `git branch`查看所有的分支（本地分支）  
* `git branch -a`查看所有的分支（包括远程分支）  
* `git branch -d branch`删除*branch*分支  
* `git branch -D branch`强制删除*branch*分支（不管branch分支上未合并的提交）  


##
##

###高级使用

* git默认对大小写不敏感  
使用`git config core.ignorecase false`使该仓库忽略大小写；  
使用`git rm <文件名>` or `git rm -r <目录名>`删除仓库中的文件或目录；  
使用`git rm --cached <文件名>`从暂存区取消该文件的暂存。  
 
* stash：暂时保存分支上对工作区的修改，使分支干净（可以切换分支）  
使用`git stash save -u "备注信息"`保存修改（-u可以保存新建的文件）;  
使用`git stash list`查看保存的所有的暂存修改；  
使用`git stash apply stash@{a}`可以应用stash@{0}保存的修改（修改全仓库可见）；  
使用`git stash clear`清除所有保存的修改。  

* asdf
