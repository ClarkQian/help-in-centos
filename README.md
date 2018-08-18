一.安装Git

$ yum install git
二. 生成SSH密钥
 $ ssh-keygen -t rsa -C “your email address”
连续按3个回车（密码默认为空），得到 id_rsa 和 id_rsa.pub 文件，在/root/.ssh 下说明生成成功

三.添加密钥到Github
打开 Github，登录自己的账号后
点击自己的头像->settings->SSH And GPG Keys->New SSH key
将本地 id_rsa.pub 中的内容粘贴到 Key 文本框中，随意输入一个 title(不要有中文)，点击 Add Key 即可

四.测试
在命令行中输入

$ ssh git@github.com
会出现如下询问：

Are you sure you want to continue connecting (yes/no)?
键入yes后回车，如果出现

Hi xxx! You’ve successfully authenticated, but GitHub does not provide shell accessConnection to github.com closed.
则说明验证成功，否则可能是上述步骤中的其中几步出错了，需重新来过

在此附上git常用命令以供使用：

git clone <address>：复制代码库到本地；

git add <file> ...：添加文件到代码库中；

git rm <file> ...：删除代码库的文件；

git commit -m <message>：提交更改，在修改了文件以后，使用这个命令提交修改。

git pull：从远程同步代码库到本地。

git push：推送代码到远程代码库。

git branch：查看当前分支。带*是当前分支。

git branch <branch-name>：新建一个分支。

git branch -d <branch-name>：删除一个分支。

git checkout <branch-name>：切换到指定分支。

git log：查看提交记录（即历史的 commit 记录）。

git status：当前修改的状态，是否修改了还没提交，或者那些文件未使用。

git reset <log>：恢复到历史版本。



Git实例：

1、远程仓库README.git为空，把本地代码上传到远程仓库

echo "# Test" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:******/README.git
git push -u origin master


2、更新本地代码到远程仓库

git add README.md
git commit -m "first commit"
git push -u origin master


3、获取远程仓库中的代码到本地

git clone git@github.com:*****/README.git



4、从远程仓库同步代码更新本地代码

git pull origin master



copy from https://blog.csdn.net/u014066037/article/details/70224780
