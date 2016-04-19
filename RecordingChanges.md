# 记录每次更新到仓库 Recording Changes to the Repository

### ** 检查文件当前状态 **
```
	$ git status
		On branch master
		Your branch is up-to-date with 'origin/master'.
		nothing to commit, working directory clean
```
 1. 这说明你现在的工作目录相当干净。换句话说，所有已跟踪文件在上次提交后都未被更改过。 
 2. 此外，上面的信息还表明，当前目录下没有出现任何处于未跟踪状态的新文件，否则 Git 会在这里列出来。 
 3. 该命令还显示了当前所在分支，并告诉你这个分支同远程服务器上对应的分支没有偏离。 现在，分支名是 “master”,这是默认的分支名。

### ** 跟踪新文件 ** 
 1. 使用命令 git add 开始跟踪一个文件。 所以，要跟踪 README 文件，运行：

```
	$ git add NEWFILE.mdgit add NEWFILE.md
```
 2. 此时再运行 git status 命令，会看到 NEWFILE.md 文件已被跟踪，并处于暂存状态：
```
	$ git status
		On branch master
		Changes to be committed:
		  (use "git reset HEAD <file>..." to unstage)

    	new file:   README
```
 3. 只要在 Changes to be committed 这行下面的，就说明是已暂存状态。 
 	如果此时提交，那么该文件此时此刻的版本将被留存在历史记录中。
```
	
```
```
	
```
```
	
```