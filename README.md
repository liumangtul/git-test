## 测试命令行git功能

### 1.1.Linux
mkdir git-test -->创建目录
cd git-test    -->进入目录
pwd            -->显示路径
**/GitHub/git-test

### 1.2.初始化git
//确保目录中没有中文
git init -->git 初始化

### 1.3.把Git装进本地库需要2步 add commit
git add README.md
git commit -m '提交README.md文件'

### 1.4.放到远程库
git remote add origin git@github.com:***/git-test.git //添加到远程库
//远程库 名字 origin
#
git push -u origin master //推送到远程库origin 的master分支上- -u是与远程的master分支做关联，用在第一次创建分支时候以后就不需要-u了

### 2.1 多啦A梦的时光
git status  查看当前工作区状态
git diff    查看工作区修改的文件 ctrl+z 退出

git add README.md
git commit -m 'commit'
[master 3628164] append GPL
 1 file changed, 1 insertion(+), 1 deletion(-)

git log 查看提交历史记录

######  回到19世纪
 git reset --hard HEAD^ ^^^表示回退版本个数
#####   回到21世纪
 git reset --hard 3628164 提交时候的版本号
###### 查看commit版本号
git reflog

# ___________________________________________
未add的区域是工作区
git add 是把文件放到暂存区
git commit 放到分支上

#### 2.2 撤销
###### 撤销尚未add的文件
git checkout -- readme.txt
###### 撤销add的文件,但没有commit的
通过 git status 发现问题
git reset HEAD README.md

###### 删除文件
git rm file 删除;
git commit file -m 'remove file';
git push orgin master;


http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013743862006503a1c5bf5a783434581661a3cc2084efa000

#### 3.1 分支
创建分支:
git branch dev 创建dev分支
git checkout -b dev 创建dev并切换到该分支

切换分支:
##
git checkout dev 切换到dev分支
##

查看分支list
##
git branch  当前分支标*
##

合并分支
##
git merge dev
把dev分支合并到当前分支上
##

删除分支
##
git branch -d dev
##
删除dev分支

### 解决冲突
