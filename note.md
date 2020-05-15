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
## git diff 用来查看文件第区别
##### git diff 没有指定文件就是比较所有文件的前后区别
##### git add .之后, 就提交了, 就不再显示区别了
