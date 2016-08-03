git init  建立代码库
git add filename 添加文件
git commit -m "information" 提交
git status 仓库状态
git diff 那些未提交的改动
git log 查看提交日志
git reset --hard HEAD^  回退到上个版本
git reset --hard HEAD^^  回退到上上个版本
git reset --hard HEAD~10  回退到10个版本之前
git reset --hard commit_id  设为某个版本,可以是过去或未来，取决于commit_id
git reflog 回退后反悔，但又忘记原来的commit_id, 用此命令查看记录