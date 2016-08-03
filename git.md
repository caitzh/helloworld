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

git pull origin master 取得远程仓库代码到本地

git clone git@github.com:caitzh/helloworld.git 复制远程代码到本地

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



