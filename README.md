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


############   远程关联仓库  ###########

#删除远程origin
git remote rm origin

#把本地仓库和远程仓库关联
git remote add origin git@github.com:liuyongjiesail/Credit.git

#拉取远程仓库
git pull origin master

#合并两个仓库
git pull origin master --allow-unrelated-histories

#推送到远程仓库
git push origin master

#克隆一个远程仓库到本地 (ssh协议和http协议)
git clone git@github.com:liuyongjiesail/Credit.git
git clone https://github.com/liuyongjiesail/Credit.git


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





