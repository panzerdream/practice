# github的使用从现在开始

>作者：徐尧 联系方式：yaoxu55prc@126.com 单位：河南大学

## git命令

git是一种分布式版本控制系统，是开源的

### 1、配置git环境

```
git config --global user.name 'xuyao'
```

此命令用于设置系统用户名

```
git config --golbal user.email 'yaoxu55prc@126.com'
```

此命令用于设置系统使用的邮箱

这两部分命令用于设置当前机器的git用户的标识，也就是说后续使用git bash管理代码时，用这两种方式标志是我自己

```
git config --unset --global user.name
```

此命令用于重置当前机器的git用户名，邮箱操作类似

### 创建本地仓库

在需要创建仓库的位置执行命令```git init```就可以创建一个被git跟踪的空仓库查看当前仓库状态，会显示是否存在未跟踪或者未提交的文件

新建空仓库之后，使用```git status```查看当前文件状态

更新文件之后使用```git add```命令将文件设置为跟踪状态，使用方法为```git add .```意为跟踪所有，```git add filename```意为跟踪某具体文件

文件跟踪之后会被git系统记录，提交到分支则使用```git commit -m 'content'```将更改提交到当前所在分支（一般默认为main）,并且可以通过```git log```命令查看历次提交的信息，content替换为提交时候记录更改记录日志


## github的使用

