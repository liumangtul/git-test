# Git  

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

git push -u origin master //推送到远程库origin 的master分支上- -u是与远程的master分支做关联，用在第一次创建分支时候以后就不需要-u了

### 2.1 多啦A梦的时光机  
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

###### 未add的区域是工作区  
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
git checkout dev 切换到dev分支  

查看分支list  
git branch  当前分支标*  

合并分支  
git merge dev  
把dev分支合并到当前分支上  

删除分支  
git branch -d dev  
删除dev分支  

### 解决冲突

### 多人协作的工作模式通常是这样：  

首先，可以试图用git push origin branch-name推送自己的修改；  

如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；  

如果合并有冲突，则解决冲突，并在本地提交；  

没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！  

如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream   branch-name origin/branch-name。  

这就是多人协作的工作模式，一旦熟悉了，就非常简单。  

## 标签管理  
##### create Tag  

  git branch
  git checkout master 切换分支  
  git tag v1.0 打标签  
  git tag 查看所有标签  
  git tag v0.9 6224937  对log里的commit id 某个d打tag  
  git show tagName 查看标签信息  

  -a 指定tagName -m tag说明
  git tag -a v0.1 -m "version 0.1 released" 3628164

##### controll Tag

  git tag -d v0.1 删除tag  
  git push origin <tagname>  推送某个标签到远程  
  git push origin --tags 推送所有tag到远程  

  如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除：  
  git tag -d <tagname>  
  然后，从远程删除。删除命令也是push，但是格式如下：  
  git push origin :refs/tags/<tagname>  
