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

### 2、创建本地仓库

在需要创建仓库的位置执行命令```git init```就可以创建一个被git跟踪的空仓库查看当前仓库状态，会显示是否存在未跟踪或者未提交的文件

新建空仓库之后，使用```git status```查看当前文件状态

更新文件之后使用```git add```命令将文件设置为跟踪状态，使用方法为```git add .```意为跟踪所有，```git add filename```意为跟踪某具体文件

文件跟踪之后会被git系统记录，提交到分支则使用```git commit -m 'content'```将更改提交到当前所在分支（一般默认为main）,并且可以通过```git log```命令查看历次提交的信息，content替换为提交时候记录更改记录日志

如果直接写```git commit```则会弹出vim编辑器督促填写日志信息

### 3、文件修改提交删除恢复

文件重命名需要在图形化界面对文件重命名之后，使用```git rm 文件名```的方式删除原先的文件，尽管对文件内容没有进行更改，随后使用```git add 文件名```命令添加上新的文件名即可

在终端上可以直接使用```git mv 原文件 重命名```对文件进行重命名

该命令仍可用于转移文件目录，由于git只追踪文件，不追踪目录，所以需要手动将新增的文件转移到目录下

```
git mv a.html HTML/
//把a.html文件转移到HTML目录下
git mv HTML Web/
//把HTML目录转移到Web目录下
```

使用```git rm```命令可以对文件进行删除

```
git rm 删除的文件地址名字
git rm -r 所需要删除的目录名
```

在提交删除之前或者之后。都可以有相对的方法来恢复此次删除

在提交删除前，我们使用以下命令进行恢复

```
git checkout HEAD -- 恢复的文件名
```

如果我们已经提交了一次的修改，那我们则使用以下命令：

```
git checkout HEAD^ -- 恢复的文件名
```

其实这个，命令的本质是将文件恢复到之前跟踪的状态，HEAD一次即恢复到头（上一次），加上一个“^”即恢复到上一次的上一次，其实可以依次递增。

```git reset --hard id```是用来回滚的代码，id替换为所需要回滚到的版本号的id哈希值，或者使用```git reset --hard HEAd^```指令用来快速回滚到我们仓库的上一个版本，如果明确知道所需要回滚的是几个版本之前，则使用```git reset --hard HEAD~n```来表示具体回滚到之前n的版本

使用```git log```命令查看版本变动信息是，可以使用```git log --pretty=oneline```选项简洁输出

对于某单个文件，可以使用```git log filename```指令针对单个文件查看其更改过的版本提交修改信息。

```git reflog```用于查看当前版本库的提交历史，所有对仓库版本的迭代都会出现在这里面，包括回滚版本

### git创建分支，合并分支

使用```git checkout -b name```创建一个分支， 使用```git branch```查看当前处于哪个分支，使用```git checkout main```切换到main分支

使用```git merge```合并分支的语法是，在主分支执行```git merge dev```把dev分支合并到main分支中

使用```git branch -a```可以查看当前所有分支

使用```git branch -D name```可以删除名为name的分支

## github的使用

首先在github上注册一个账号，

然后在本地建立一个你想要存储密钥的路径，在文件夹内执行代码```ssh-keygen -t rsa -C "邮箱地址"```，建立一个ssh的key

然后所有可选项都可以都直接回车设置默认值

然后id_rsa,id_rsa.pub就会自动添加到刚才所选的文件夹中了

接着在github上添加公钥，把id_rsa.pub文件的内容复制到“setting-SSH and GPG keys-SSH keys”，按照界面要求即可


