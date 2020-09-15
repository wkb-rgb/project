## git stash

***git stash save "first"*** 　　　　　　保存并隐藏目前的修改，这样可以进行其他修改工作

***git stash apply stash@{０}*** 　　　重新将保存的更改进行应用

***git stash list*** 　　　　　　　　　查看所有保存

***git stash pop*** 　　　　　　　　　弹出最新保存的修改，会删除这个弹出的修改

**在push代码前，可以先保存修改，然后pull远程的代码到本地，再将修改放出来查看是否有冲突并进行修改，然后再add  commit    push**

https://www.cnblogs.com/zndxall/archive/2018/09/04/9586088.html

---------------------------------------------------------------------

## git cherry-pick

***git cherry-pick  commitHash***        　　　将一个分支的commit添加到令一个分支

http://www.ruanyifeng.com/blog/2020/04/git-cherry-pick.html

-------------------------------------------------

## git conifg

***git config --list***  　　　　　　　　　　　　　　显示当前git配置

***git config [--global] user.name "Username"***　　 配置提交代码时用户名

***git config [--global] user.email "email"***  　　　　配置提交代码时邮箱

-------------------------------------------------------

## 分支

| 命令                                   | 作用                           |
| -------------------------------------- | ------------------------------ |
| git branch                             | 列出所有本地分支               |
| git branch -r                          | 列出所有远程分支               |
| git branch -a                          | 列出所有本地和远程分支         |
| git branch [branch name]               | 新建分支，但不切换到该分支下   |
| git checkout -b [branch]               | 新建分支，并切换到该分支下     |
| git checkout [branch name]             | 切换该分支                     |
| git checkout -                         | 切换到上一个分支               |
| git merge [branch]                     | 合并指定分支到当前分支         |
| git branch -d [branchname]             | 删除分支                       |
| git push origin --delete [branch-name] | 删除远程分支                   |
| git cherry-pick [commit]               | 选择一个commit，合并进当前分支 |

**关于git checkout [branchname],假如在远程存在一个分支名为test而本地不存此分支时执行git checkout test，则会在本地新建一个分支test并pull远程的test分支的内容到本地。**

--------------------------

## 撤销

1.未执行git add

***git checkout .***  　　　　　　　 放弃所有未git add的本地修改

***git checkout --filepathname*** 　 放弃指定文件的修改，注意是两道杠

2.已执行git add，未执行git commit

***git reset HEAD filepathname*** 　　相当于撤销git add操作，但本地修改不会消失

3.已执行git commit

***git reset --hard HEAD^***　　　　 回退到上一次commit的状态

***git reset --hard HEAD^^*** 　　 　回退到上上次commit的状态，以此类推。往上一百个版本就是HEAD~100

***git reset --hard commitId***　　　 回退到任意一次提交版本

-----------------------------

## 查看信息

| 命令                         | 作用                                     |
| :--------------------------- | :--------------------------------------- |
| git status                   | 显示有变更的文件                         |
| git log                      | 显示当前分支的版本历史                   |
| git diff                     | 显示工作区和暂存区的差异                 |
| git diff HEAD                | 显示工作区与当前分支最新commit之间的差异 |
| git show [commit]            | 显示某次提交的元数据和内容变化           |
| git show [commit]:[filename] | 显示某次提交时，某个文件的内容           |
| git reflog                   | 显示当前分支的最近几次提交               |

-------------------------

## 远程同步

| 命令                        | 作用                       |
| --------------------------- | -------------------------- |
| git push [remote] [branch]  | 上传到远程分支             |
| git  pull [remote] [branch] | 拉取远程分支               |
| git push [remote] --force   | 强制推送到远程，即使有冲突 |
| git push [remote] --all     | 推送所有分支到远程仓库     |
| git fetch [remote]          | 拉取远程主机的全部更新     |
| git fetch [remote] [branch] | 拉取指定分支的更新         |



----------

