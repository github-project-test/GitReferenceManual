# Git Reference Manual

@(参考手册)[how to use git shell|帮助|Markdown]
- **直接记录快照，而非差异比较** ：
- **近乎所有操作都是本地执行** ：
- **时刻保持数据完整性** ：
- **多数操作仅添加数据** ：
- **文件的三种状态** :
对于任何一个文件，在 Git 内都只有三种状态：已提交（committed），已修改（modified）和已暂存（staged）。已提交表示该文件已经被安全地保存在本地数据库中了；已修改表示修改了某个文件，但还没有提交保存；已暂存表示把已修改的文件放在下次提交时要保存的清单中。

由此我们看到 Git 管理项目时，文件流转的三个工作区域：Git 的工作目录，暂存区域，以及本地仓库。
![git文件三种状态](https://raw.githubusercontent.com/github-project-test/GitReferenceManual/master/images/1.png)
