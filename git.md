## 基本命令
git init  建立代码库

git add filename 添加文件

git commit -m "information" 提交

git status 仓库状态

git diff 那些未提交的改动

git log 查看提交日志

## 版本回退
git reset --hard HEAD^  回退到上个版本

git reset --hard HEAD^^  回退到上上个版本

git reset --hard HEAD~10  回退到10个版本之前

git reset --hard commit_id  设为某个版本,可以是过去或未来，取决于commit_id

git reflog 回退后反悔，但又忘记原来的commit_id, 用此命令查看记录

## 撤销修改
git checkout -- file 撤销工作区的修改（还没有add或commit）

git reset HEAD file 撤销上次add的修改，使暂存区回到上次状态（还没commit）,之后再使用上行命令撤销工作区的修改

## 远程仓库
git remote add origin git@github.com:caitzh/helloworld.git 关联远程代码库

git push -u origin master 推送到远程代码库, **第一次加-u**, Git就会把本地的master分支和远程的master分支进行关联起来, 我们以后的push操作就不再需要加上-u参数了

git push origin dev 推送本地dev分支到远程dev分支, 若有冲突, 需pull到本地解决冲突后再提交, 若pull失败先执行下面命令再pull

git branch --set-upstream dev origin/dev 将本地dev分支与远程dev分支关联起来,否则上面的pull远程dev分支会失败

git pull origin master 取得远程仓库代码到本地

git clone git@github.com:caitzh/helloworld.git 复制远程代码库到本地(会在本地新建一个代码库, Git自动把本地的master分支和远程的master分支对应起来)

git remote 查看远程仓库信息, 加**-v**显示详细信息

## 分支(branch)
查看分支：git branch

创建分支：git branch *new_branch_name*

切换分支：git checkout *new_branch_name*

创建+切换分支：git checkout -b *new_branch_name*

合并某分支到当前分支：git merge *new_branch_name*, 合并分支出现冲突时，需要手动解决冲突，并重新add, commit

删除分支：git branch -d *new_branch_name*

强制删除未合并的分支：git branch -D *new_branch_name*

查看冲突记录：git log --graph --pretty=oneline --abbrev-commit

禁用Fast forward的合并：git merge --no-ff -m "merge with no-ff" dev , 这样合并时会commit, log能看到分支记录, 而Fast forward则看不出曾经有过分支

## 保存工作现场
git stash 当前工作分支还无法提交又需要转去别的分支时, 用此命令保存现场在stash

git stash list 查看stash内容(可能有多个)

git stash apply 恢复工作现场但不删除 stash

git stash drop 删除 stash

git stash pop 恢复工作现场同时删除 stash, 相当于上面两条命令结合

git stash apply stash@{0} 当stash有多个工作现场时, 恢复指定下标的那个

## 标签管理

####以下的v1.0, v2.0等均为示例的标签名, 可自行更改

git tag v1.0 在当前分支的最新提交的commit上打上标签 "v1.0"

git tag v2.0 commit_id 在对应commit_id的那次commit打上标签

git tag 查看标签(按字母排序)

git show v1.0 查看对应标签的信息

git tag -a v0.1 -m "version 0.1 released" commit_id 创建带有说明的标签，用-a指定标签名，-m指定说明文字

git tag -d v0.1 删除标签

git push origin v1.0 推送对应标签到远程

git push origin --tags 推送全部尚未推送到远程的本地标签

git push origin :refs/tags/v0.9  删除远程标签

## 参与开源项目

1. 在其项目主页点击**Fork**, 复制一份到自己的github上

2. 从自己的github上 clone 到本地

3. 完成后推送到自己的github上

4. 想让对方接受你的修改, 可以在GitHub上发起一个pull request(对方不一定接受)

## git ignore

创建.gitignore文件, 里面写上忽略的文件名

git add filename 尝试添加已忽略文件时会报错, 解决方法如下：

1. git add -f filename 加**-f**参数, 强制添加已忽略的文件

2. git check-ignore -v filename 查看ignore文件, 看哪一行忽略了此filename, 并修改ignore文件


## git 颜色

git config --global color.ui true  让 git 命令行显示颜色

## 命令简化

git config --global alias.st status 用 st 作为status的别名, 之后只要输入"git st"即相当于"git status"

git config --global alias.ci commit 同理, 用"git ci" 代替 "git commit"

--global 是全局的意思, 即对当前用户的所有仓库起作用, 不加则只对当前仓库有效

每个仓库的Git配置文件都放在.git/config文件中, 里面的[alias]即别名, 命令简化也可直接修改此文件

当前用户的Git配置文件放在用户主目录下(如"C:\Users\Administrator\")的一个隐藏文件.gitconfig中





