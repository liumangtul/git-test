## 测试命令行git功能

### 1.Linux
mkdir git-test -->创建目录
cd git-test    -->进入目录
pwd            -->显示路径
**/GitHub/git-test

### 2.初始化git
//确保目录中没有中文
git init -->git 初始化

### 3.把Git装进本地库需要2步 add commit
git add README.md
git commit -m '提交README.md文件'

### 4.放到远程库
git remote add origin git@github.com:***/git-test.git //添加到远程库
//远程库 名字 origin
#
git push -u origin master //推送到远程库origin 的master分支上- -u是与远程的master分支做关联，用在第一次创建分支时候以后就不需要-u了
