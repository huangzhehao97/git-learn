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
##### 使用git rm test.md命令移除了提交的test.md
##### 再使用命令来重命名文件: git mv test.md new.md
##### 提交: git add .
		  : git commit -m "提交"
		  : git push
