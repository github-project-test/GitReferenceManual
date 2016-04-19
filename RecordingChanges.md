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

4.现在，让我们在项目下创建一个新的 NEWFILE.md 文件。 如果之前并不存在这个文件，
   使用 git status 命令，你将看到一个新的未跟踪文件：

```
	$ echo 'My Project' > README
	$ git status
	On branch master
	Untracked files:
	  (use "git add <file>..." to include in what will be committed)

	    README

	nothing added to commit but untracked files present (use "git add" to track)
```
5. 在状态报告中可以看到新建的 README 文件出现在 Untracked files 下面。
    未跟踪的文件意味着 Git 在之前的快照（提交）中没有这些文件；
    Git 不会自动将之纳入跟踪范围，除非你明明白白地告诉它“我需要跟踪该文件”， 这样的处理让你不必担心将生成的二进制文件或其它不想被跟踪的文件包含进来。 不过现在的例子中，我们确实想要跟踪管理 README 这个文件。

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