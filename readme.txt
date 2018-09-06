Git is distributed free software.
Git is free software.


安装好git后，输入命令
git config --global user.name "用户名"
git config --global user.email "邮箱"

创建版本库
mkdir learngit //创建目录
cd learngit    //定位到learngit
pwd   //查看当前目录
git init //这是git管理的仓库

vi readme.txt //创建readme.txt文件
Esc  //退出可编辑模式
：wq  //保存退出
git add readme.txt //把文件添加到git仓库
git commit -m "备注说明"
可添加多个文件：
git add file1.txt
git add file2.txt file3.txt
git commit "add 3 files."

初始化一个Git仓库，使用git init命令
添加文件到Git仓库，分两步：
1.使用命令 git add <file>,注意，可反复多次使用，添加多个文件；
2.使用命令 git commit -m <message>，完成

git status  //查看当前仓库的状态
git diff readme.txt //查看对readme的修改

要随时掌握工作区的状态，使用git status命令。
如果git status 告诉你有文件被修改过，用git diff 可以查看修改内容。

版本倒退
git log --pretty=oneline  //git log 输出信息太多时可用
HEAD指向的版本就是当前的版本，因此，git允许我们在版本的历史之间穿梭，使用命令gitreset --hard commit_id.
穿梭前，用git log 可以查看提交历史，以便确定要回退到哪个版本。
要重返未来，用git reflog 命令查看历史，以便确定要回到未来的哪个版本。
git reset --hard HEAD^ //返回上一个版本  上上版本HEAD^^  100以上用HEAD~100

没进暂存区撤销修改
git chechout -- readme.txt
git add <file> 存进了暂存区
想修改git reset HEAD <filename> --> git chechout -- <filename>
提交了（git commit -m “备注说明修改了什么”），只能版本回退。

rm text.txt //删除文件text.txt
确定删除：git rm text.txt
          git commit -m "remove texxt.txt" //从版本库删除了文件

或还原：git checkout -- test.txt

远程仓库  登陆GitHub，New repository-->Repository name(learngit)-->create repository //创建了learngit仓库
把本地仓库的内容推送到GitHub仓库：
git remote add origin git@github.com:MaiHuaJ/learngit.git
MaiHuaJ是我的GitHub账号名
查看自己的key
cat ~/.ssh/idrsa.pub
复制好key，上传key：
Edit profile--> SSH and GPG keys-->New SSH key-->粘贴进key-->Add SSh key
在git Base使用命令ssh -T git@github.com测试公钥是否添加成功。
git push -u origin master //把本地库的所有文件推送到远程库上。
从现在起，只要本地做了提交，就可以通过命令：
git push origin master
从远程库克隆：
git clone git@github.com:MaiHuaJ/gitskills.git

