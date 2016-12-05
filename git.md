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
使用`git rm <文件名>` or `git rm -r <目录名>`删除工作去和仓库中的文件或目录；  
使用`git rm --cached <文件名>`从暂存区取消该文件的暂存。  
 
* **stash**：暂时保存分支上对工作区的修改，使分支干净（可以切换分支）  
使用`git stash save -u "备注信息"`保存修改（-u可以保存新建的文件）;  
使用`git stash list`查看保存的所有的暂存修改；  
使用`git stash apply stash@{0}`可以应用stash@{0}保存的修改（修改全仓库可见）；  
使用`git stash clear`清除所有保存的修改。  

* **clean**:删除文件（删除工作区的文件和目录/最后commit之后的修改）  
`git clean -n` 显示将要删除的文件(只会显示将要删除的文件，不包括目录)  
`git clean -fd -n` or `git clean -f -d -n` 显示将要的删除的文件和目录  
`git clean -f -d` or `git clean -fd` 删除文件和目录  
  
* **reset**:将当前分支重设到指定的<commit>或者HEAD(默认)    
分支干净：（最后一次commit之后没有进行任何修改）  
`git reset --hard commitId` 撤销最近一次的*commit*、*add*、*modiffy*操作   
`git reset --mixed commitId` (默认参数) 撤销最近一次的*commit*、*add*操作  
`git reset --soft commitId` 撤销最近一次的*commit*操作   

* **rm**: 从工作区和暂存区将文件删除  
`git rm filename` 将文件*filename*从*workspce*和*stage*中删除  
`git rm --cached filename` 将文件*fiename*从*stage*中删除  
`git rm -r dir` 递归的删除目录*dir*  
两个参数可以结合使用

* **diff**: 比较*workspce*和*stage*或者*repertory*之间已经被追踪的文件内容的差别  
`git diff ` 比较*workspace*和*stage*之间的文件差别  
`git diff HEAD` 比较*workspace*和*repertory*之间的文件差别  
`git diff --staged` or `git diff --cached` 比较*stage*和*repertory*之间的差别

* **tag**:  


* **merge**:  

* **rebase**:  

* **revert**:

* **submodule**：