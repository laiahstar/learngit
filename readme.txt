Git is a versin control system.
Git is a free software.
Git is a distributed version control system.
Git is free software.
Git tracks changes
Git tracks changes of files.
git init  --创建一个新目录，进入该级目录后，把目录变成Git可以管理的仓库
git add readme.txt  --编写readme.txt,使用git add添加到Git仓库目录下
git commit -m "说明的内容"  --提交文件,-m后面输入的是本次提交的说明
git status 要随时掌握工作区的状态
如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

git checkout -- file  ##git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令