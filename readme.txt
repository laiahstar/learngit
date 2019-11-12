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
#撤销更改
git checkout -- file 丢弃工作区的更改，从工作区回退 ##git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令
git reset HEAD <file> 从暂存区回到工作区，再利用工作区撤销更改的方式进行回退
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

Creating a new branch is quickly.
Creating a new branch is quick & simple.