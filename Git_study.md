[TOC]

# Git使用指南（Windows版）

## 分布式VS集中式版本控制

集中式版本控制（CVS/SVN）

- 本地A上传至中央服务器C，本地B从中央服务器C下载修改再上传至C

分布式版本控制

- 每个人电脑上都有一份完整版
- 发生修改时只交换修改部分



##   Git安装

Windows进入[官网](https://git-scm.com/downloads)下载软件安装。安装完成后启动`Git Bash `，开启命令行窗口。

1. 初始化用户名和邮箱

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

2. 创建本地版本库/仓库（repository）

在想要用作仓库的地方新建一个文件夹，命名为`GitHub`（随便命名）。在此目录下，右键-Git Bash Here，打开命令行窗口。

输入`git init`，即可把这个目录变成Git可以管理的仓库。

添加文件到Git仓库，分两步：

​	 `git add <file>`，添加文件

​	 `git commit -m <message>`，完成

3. 修改文件

   `git status`  查看仓库当前的状态

   `git diff`  查看修改内容 

   `git log `  查看所有修改记录 `--pretty=oneline `

   `git add`  添加修改

   `git commit -m "xiugai"`  确认修改

   ![git流程图](https://upload-images.jianshu.io/upload_images/152050-0ccc1cf8b80fe38e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4. 回归之前版本

   上个版本`HEAD^`，上上版本`HEAD^^ ` ，上100个版本`HEAD~100` 

   `git reset --hard HEAD^`  回滚上一个版本

   `cat README.md`  查看修改后内容

   `git reflog`  记录了对文件的每一次操作

   `git reset --hard commit_id`  回滚ID指向的版本

   `git log`  查看提交历史，以便确定要回退到哪个版本 

   `git reflog`  查看命令历史，以便确定要回到未来的哪个版本 

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file`。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD <file>`，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考[版本回退](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013744142037508cf42e51debf49668810645e02887691000)一节，不过前提是没有推送到远程库。

`git rm`用于删除一个文件 



创建SSH KEY。先看一下你C盘用户目录下有没有.ssh目录，有的话看下里面有没有id_rsa和id_rsa.pub这两个文件，有就跳到下一步，没有就通过下面命令创建

```
   $ ssh-keygen -t rsa -C "youremail@example.com"
```

​       

然后一路回车。这时你就会在用户下的.ssh目录里找到id_rsa和id_rsa.pub这两个文件   

​      ![img](https://img-blog.csdn.net/20170414170253668) 















































