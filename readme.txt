Git is a distributed version control system.
Git is free software distributed under the GPL.


把一个文件放到Git仓库只需要两步：
1、用命令git add 告诉git，把文件添加到仓库
  $git add readme.txt

2、用命令git commit告诉Git，把文件提交到仓库。
  $git commit -m "wrote a readme file"

  -m后面输入的是本次提交的说明

 git add即是把文件修改添加到暂存区
 git commit 提交更改，实际上就是把暂存区的所有内容提交到当前分支。


为什么git添加文件需要add、commit两步呢？因为commit 可以一次提交很多文件。
	
小结：
	要随时掌握工作区的状态，使用git status命令
	如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

使用git log命令查看提交日志。
若显示信息太多，可用--pretty=oneline参数查看



使用git reset命令回退版本.当前版本用HEAD表示。上一个版本为HEAD^,上上个版本为HEAD^^,往上一百个版本HEAD~100

test  test  test reset

git提供了一个命令git reflog来记录你的每一次命令


小结：
	HEAD指向的版本就是当前版本，因此，git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id
	穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本
	要重返未来，用git reflog查看命令历史


每次修改，如果不用git add到暂存区，那就不会加入到commit 中。
git追踪的是修改，而不是文件。

撤销修改
git checkout --filename
意思是，将filename文件在工作区的修改全部撤销，有两种情况：
1、文件自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态
2、文件已经添加到暂存区后，又做了修改，现在，撤销修改就回到添加到暂存区后得状态。

该命令中--很重要，如没有，就变成了“切换到另一个分支”命令
