git toturial
$ mkdir models # 创建一个与要clone的仓库同名或不同命的目录models文件夹，
$ cd models//进入models文件夹
$ git init #初始化
$ git remote add origin  https://github.com/tensorflow/models.git # 增加远端的仓库地址
$ git config core.sparsecheckout true # 设置Sparse Checkout 为true 
$ echo "research/deeplab" >> .git/info/sparse-checkout # 将要部分clone的目录相对根目录的路径写入配置文件
$ git pull --depth 1 origin master #pull下来代码 最新的一层

------------------------------------------------------------------------------------------------------------------
WorkingDirectory--@--Stage(Index)--@--Repository(Head)

工作区域（Working Directory）就是你平时存放项目代码的地方。

暂存区域（Stage）用于临时存放你的改动，事实上它只是一个文件，保存即将提交的文件列表信息。

Git 仓库（Repository）就是安全存放数据的位置，这里边有你提交的所有版本的数据。其中，HEAD 指向最新放入仓库的版本（这第三棵树，确切的说，应该是 Git 仓库中 HEAD 指向的版本）。

Git 的工作流程一般是：

在工作目录中添加、修改文件；

将需要进行版本管理的文件放入暂存区域；

将暂存区域的文件提交到 Git 仓库。

因此，Git 管理的文件有三种状态：已修改（modified）、已暂存（staged）和已提交（committed），依次对应上边的每一个流程。

------------------------------------------------------------------------------------------------------------------

git update-git-for-windows

使用git@github必须使用ssh使用
Git bash 
$ ssh-keygen -t rsa -C "你自己注册GitHub的邮箱" 生成ssh-rsa码在C:\Users\Qurner\.ssh的id_rsa.pub文件下
之后在GitHub的SSH添加
对某个文件夹从本地WorkingDirectory--@--Stage(Index)--@--Repository(Head)
$ ssh -T git@github.com登录链接本地git和GitHub库
git config --global user.name "Tokoshie"
git config --global user.name "sinkqingmu@gmail.com"
mkdir flondname
cd 
git init 
git status
git config --list

-----------------------------------------------------------------------------------------------------------------
Git基本常用命令如下：
   mkdir：         XX (创建一个空目录 XX指目录名)
   pwd：          显示当前目录的路径。
   git init ：         把当前的目录变成可以管理的git仓库，生成隐藏.git文件。
   git add XX ：      把xx文件添加到暂存区去，添加后git会开始tracked该文件的变更和记录
   git commit -m “comment something” /提交文件 –m 后面的是注释。add后用该命令添加comment(注释)
   git status：        查看仓库状态
   git diff  XX ：     查看XX文件修改了那些内容
   git log ：         查看历史记录
   git reset  --hard HEAD^ ：或者 git reset  --hard HEAD~ 回退到上一个版本
                        (如果想回退到100个版本，使用git reset --hard HEAD~100 )
   cat XX   ：      查看XX文件内容
   git reflog  ：     查看历史记录的版本号id
   git checkout -- XX ： 把XX文件在工作区的修改全部撤销。从stage上的add 内容返回给workingdirectory
   git rm XX  ：        删除XX文件
   git remote add XXX https://github.com/XXX.git： 关联一个远程库repository才能remote
   git push -u(第一次要用-u 以后不需要) origin master ：把当前master分支推送到远程库
   git clone https://github.com/RTplay/testgit.git ： 从远程库中克隆
   git checkout -b dev ： 创建dev分支 并切换到dev分支上
   git branch  ：查看当前所有的分支
   git checkout master ：切换回master分支
   git merge dev    ：在当前的分支上合并dev分支
   git branch -d dev ：删除dev分支
   git branch name  ：创建分支
   git stash ：把当前的工作隐藏起来 等以后恢复现场后继续工作
   git stash list ：查看所有被隐藏的文件列表
   git stash apply ：恢复被隐藏的文件，但是内容不删除
   git stash drop： 删除文件
   git stash pop： 恢复文件的同时 也删除文件
   git remote： 查看远程库的信息
   git remote -v ：查看远程库的详细信息
   git push origin master  ：Git会把master分支推送到远程库对应的远程分支上