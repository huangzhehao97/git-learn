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
##### git mv 旧的文件的名字 新的文件的名称(或者添加路径来给旧的文件移动到新的位置)

## 5. 使用git命令删除文件
##### 删除文件: git rm 文件名
##### 删除多个文件时, 文件名之间通过空格分格
##### 删除整个目录的时候使用-r 表示递归的删除目录中的所有的文件: git rm -r test

## 6. 恢复删除的文件
##### git checkout HEAD -- 恢复到上一次提交
##### 创建文件: touch new.md
##### 提交代码变动: git add .
				  : git comm-m "add new.md"
##### 删除文件: git rm new.md
##### 恢复删除的文件: git checkout HEAD -- new.md
##### 提交代码: git push

## 7. 恢复文件到历史版本 git revert
##### 使用git commit的id号恢复到对应的版本
##### 使用命令重命名文件: git mv new.md new2.md
##### 提交这次的代码的改动
##### 修改new2.md文件内的内容
##### 提交: git add .
		  : git commit "修改new2.md"的内容
##### 使用git log --oneline来方便的查看所有的提交, 第一行是独一无二的commit id
##### shiyo使用命令: git revert [commit id], 从而使得代码恢复到[commit id]对应的提交的时候的代码的情况
##### 以上的代码实现了代码通过commit id跳转到对应的代码

## 8. 重制提交--控制头部的指针 git reset
##### --soft: 重制提交到对应的位置, 同时将当时代码的改变放入缓存区
##### --mixed: 重制提交到对应的位置, 不将代码放入到缓存区
##### --hard: 重制提交到对应的位置, 将缓存区的改变提交了

## 9. 日志
##### 
##### git log --oneline --before="2014-07-05" 用来查找一定日期之前的日志信息, 同时设置输出的样式
##### 打印在某一个时间之前的日志 git log --oneline --before="2020-05-16"
