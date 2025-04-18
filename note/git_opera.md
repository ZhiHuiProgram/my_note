# git 操作

初始化
```
cd /path/to/your/project  # 进入你的项目目录
git init                  # 初始化git仓库
```
添加文件到缓存
```
git add filename
or
git add .
```
提交到本地工程
```
git commit -m "第一次提交，初始化工程"
```
添加远程仓库
```
git remote add origin https://github.com/你的用户名/你的仓库名.git
```
push仓库
```
git branch //查看本地仓库名
git push -u origin master// master or main
"-u 的意思是以后你只需要 git push，不用每次都指定远程和分支。"
"以后修改文件后，只需要 add -> commit -> push。"
```
本地改名
```
git branch -M main
```
查看远程连接
```
git remote -v 
```
更换仓库远程连接
```
git remote set-url origin(仓库名称) https://github.com/newusername/newproject.git（远程链接）
```
