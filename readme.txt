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

