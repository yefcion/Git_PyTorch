[TOC]

# Git使用指南（Windows版）

## 分布式VS集中式版本控制

集中式版本控制（CVS/SVN）

- 本地A上传至中央服务器C，本地B从中央服务器C下载修改再上传至C

分布式版本控制

- 每个人电脑上都有一份完整版
- 发生修改时只交换修改部分



##   Git安装与使用

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

   `git rm`  用于删除一个文件 

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

   

   **场景1：**当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file`。

   **场景2：**当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD <file>`，就回到了场景1，第二步按场景1操作。

   **场景3：**已经提交了不合适的修改到版本库时，想要撤销本次提交，参考[版本回退](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013744142037508cf42e51debf49668810645e02887691000)一节，不过前提是没有推送到远程库。

5. 克隆/更新GitHub上的仓库(Repository)

   `git clone <仓库地址>`  从GitHub上clone项目到本地

   `git push`  将本地修改推送到GitHub



## 常用功能汇总

- 创建版本库 (init)
- 添加文件管理 (add)
- 提交修改 (commit)



```python
cd `本地仓库路径`
git config --global user.name "用户名"
git config --global user.email "电子邮件"

# 查看用户信息
git config user.name
git config user.email

# 清屏
clear

# 显示所有文件
ls -a

# 查看仓库中文件状态
git status
git status -s # 缩写形式
git diff # 查看不同

# 将本地添加的文件添加进仓库
git add `文件名.类型`
git add . # git所有的改变

# 提交修改
git commit -m "change_1" # -m "添加修改注释" 

# 查看修改日志
git log

# 推到GitHub
git push
```









































