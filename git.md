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




