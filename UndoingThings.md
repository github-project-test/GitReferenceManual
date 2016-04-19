#  撤消操作 Undoing Things

##  git commit --amend
```
Mac-Pro: jasper$  git commit --amend
```
 1. 有时候我们提交完了才发现漏掉了几个文件没有添加，或者提交信息写错了。
 	可以使用这个命令，最终你只会有一个提交 - 第二次提交将代替第一次提交的结果。

## 取消暂存的文件
```
Mac-Pro: jasper$  git add *
			   $  git status
				   On branch master
				   Changes to be committed:
				        (use "git reset HEAD <file>..." to unstage)

					    renamed:    README.md -> README
					    modified:   CONTRIBUTING.md
```
 1. 有时候我们使用add增加了当前目录所有文件暂存，而我们原本想单独提交；
 2. 怎么取消暂存了？？我们可以使用 git reset HEAD Contributing_file_name

## 撤消对文件的修改
 1. 如果你并不想保留对 CONTRIBUTING.md 文件的修改怎么办？ 你该如何方便地撤消修改 - 
 2. 将它还原成上次提交时的样子（或者刚克隆完的样子，或者刚把它放入工作目录时的样子）？ 
 3. 幸运的是，git status 也告诉了你应该如何做。 在最后一个例子中，未暂存区域是这样：
```
$ git checkout -- CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    renamed:    README.md -> README

```

