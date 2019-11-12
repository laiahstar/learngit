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

Creating a new branch is very quickly.

要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>或者git switch <name>

创建+切换分支：git checkout -b <name>或者git switch -c <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

##解决冲突
查看分支的合并情况：git log --graph --pretty=oneline --abbrev-commit
当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容，再提交。

用git log --graph命令可以看到分支合并图。

##分支管理策略
git stash 当接到临时调整的任务，同时当前任务不能commit的时候，可以先保存当前工作区，然后切换到其它分支去执行任务
git stash list 用于查看刚才保存的工作现场
git stash apply 恢复，然后删除stash内容，使用git stash drop
git stash pop ,恢复的同时把stash内容也删除
##Feature分支
开发一个新的分支，如果要丢弃一个没有被合并过的分支，可以通过 git branch -D <name>强行删除分支

##标签管理
发布一个版本时，我们通常先在版本库中打一个标签（tag），这样，就唯一确定了打标签时刻的版本。将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。
创建标签：
默认标签是打在最新提交的commit上的。有时候，如果忘了打标签，方法是找到历史提交的commit id，然后打上就可以了
查看commit id命令：git log --pretty=oneline --abbrev-commit 
命令git tag <tagname>用于新建一个标签，默认为HEAD，也可以指定一个commit id；
命令git tag -a <tagname> -m "blablabla..."可以指定标签信息
命令git show <tagname> 可以查看标签的说明文字
命令git tag可以查看所有标签。
操作标签：
命令 git tag -d <tagname> 用于删除标签
