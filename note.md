# 学习git的笔记
## 1. 创建别名
##### 使用命令, 命令的作用域为所有用户: git config --global alias.co checkout
##### 在~/.gitconfig配置文件中会有体现
```bash
[user]
	email = huangzhehaocool@163.com
	name = HuangZheHao
[alias]
	co = checkout
```
## 2. git diff 用来查看文件第区别
##### git diff 没有指定文件就是比较所有文件的前后区别
##### git add .之后, 就提交了, 就不再显示区别了

## 3. 在文件系统上重命名git跟踪的文件
##### 创建测试文件: touch test.md 
##### 添加改动: git add .
##### 提交代码: git commit -m "测试重命名"
##### 直接将test.md的名字改为new.md, 再用git status可以看到删除了test.md, 增加了new.md没有提交变更
##### 使用命令移除test.md的提交记录: git rm test.md
##### 使用命令添加new.md来提交new.md: git add new.md
##### 从而成功的在文件系统上手动的将文件重命名
##### 提交: git add .
		  : git commit -m "提交"
		  : git push

## 4. 使用git命令来重命名文件
##### 使用git mv 命令来实现文件的重命名和移动
##### git mv fileName newFileName
