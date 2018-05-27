第一个版本管理库

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
git sdd . # git所有的改变

# 提交修改
git commit -m "change_1" # -m "" 添加修改注释

# 查看修改日志
git log

# 推到GitHub
git push
```



