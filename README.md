# Credit


############   本地仓库  ###########

#把当前目录变为git仓库
git init

#查看工作区修改状态
git status

#查看工作区所有文件修改不同对比
git diff

#查看工作区某个文件修改不同对比
git diff text.txt

#把当前目录下所有文件从工作区添加进入暂存区
git add .

#将text.txt文件从工作区添加进入暂存区
git add text.txt

#把暂存区的修改提交到git仓库（ -m '修改说明'）
git commit -m "add distributed"

#查看某个文件内容
cat text.txt

#回退到指定版本
git reset a9d00b7

#回退到上一次修改
git reset --hard HEAD^

#查看修改历史
git reflog

#查看commit log
git log --pretty=oneline

#Git删除某个文件
git rm test.txt

#恢复上一步操作
git checkout -- test.txt

#撤销本地所有修改
git checkout .

############   远程关联仓库  ###########

#删除远程origin
git remote rm origin

#把本地仓库和远程仓库关联
git remote add origin git@github.com:liuyongjiesail/Credit.git

#拉取远程仓库
git pull origin master

#合并两个仓库
git pull origin master --allow-unrelated-histories

#推送到远程仓库master
git push origin master

#克隆一个远程仓库到本地 (ssh协议和http协议)
git clone git@github.com:liuyongjiesail/Credit.git
git clone https://github.com/liuyongjiesail/Credit.git

#将本地分支与远程分支关联
git branch --set-upstream-to origin/newName

############   分支  ###########
#创建并切换到dev分支
git checkout -b dev

#创建分支
git branch dev

#切换分支
git checkout dev

#查看所有分支
git branch

#合并分支
git merge dev

#删除分支
git branch -d dev

#查看合并分支图
git log --graph
git log --graph --pretty=oneline --abbrev-commit

#注意：如果你目前在一个分支上开发功能，但是临时要在另一个分支上修复bug，但是你在目前的分支上已经做了很多修改而又不想commit（为什么在切换分支的时候一定要commit呢？ 其实不commit，也能切换分支，但是会把工作区的修改一起带过去到切换的分支上，这不是我想要的，所以说一般切换分支都要进行commit，原则就是“切换分支过去，给它一个比较干净纯洁的工作区”），可以用git stash把修改保存在当前分支的存储区，回来的时候再用命令 git stash pop（这个命令进行了两个操作 git stash apply -- 恢复， git stash drop -- 删除） 把存储的内容还原回工作区

#查看储存区的内容
git stash list

#把工作去的内容储存起来
git stash

#恢复内容
git stash apply

#删除储存区内容
git stash drop

#恢复并删除
git stash pop


#************************  标签 ****************************

#打一个标签
git tag v1.0

#查看所有标签
git tag

#对某次commit打一个标签
git tag v0.9 6224937

#查看某次tag
git show v0.9

#对某次commit打标签，并加说明
git tag -a v0.1 -m "version 0.1 released" 3628164

#对某次commit打一个标签，并PGP签名标签
git tag -s v0.2 -m "signed version 0.2 released" fec145a

#删除某个标签
git tag -d v0.1

#推送某个标签到远程
git push origin v1.0

#一次性推送全部尚未推送到远程的本地标签
git push origin --tags

#删除远程标签
git push origin :refs/tags/v0.9


#**************************  实用命令  **************************

#删除远程的某次commit，先回退到某次提交，然后强制推送到远程
git reset --hard 12345    
git push --force

#值得注意的是，这类操作比较比较危险，例如：在你的commit 3之后别人又提交了新的commit 4，那在你强制推送之后，那位仁兄的commit 4也跟着一起消失了。

#修改最近一次的提交说明
git commit --amend

#如果远程已经修改,强制提交
git push -f

#把目前的修改同步提交到上一次commit
git add .
git commit --amend






