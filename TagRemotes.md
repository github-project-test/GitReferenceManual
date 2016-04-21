# 标签 检索 创建 。

## Git 使用两种主要类型的标签：
 1:  轻量标签（lightweight）与附注标签（annotated）。
 1.1: 一个轻量标签很像一个不会改变的分支 - 它只是一个特定提交的引用。
 1.2: 然而，附注标签是存储在 Git 数据库中的一个完整对象。 它们是可以被校验的；
 1.3: 其中包含打标签者的名字、电子邮件地址、日期时间；还有一个标签信息；
 1.4: 并且可以使用 GNU Privacy Guard （GPG）签名与验证。 
 2: 通常建议创建附注标签，这样你可以拥有以上所有信息；但是如果你只是想用一个临时的标签，或者因为某些原因不想要保存那些信息，轻量标签也是可用的。

### 列出标签
 Mac$: git tag 

### 附注标签
 1: 在 Git 中创建一个附注标签是很简单的。 最简单的方式是当你在运行 **tag 命令时指定 -a 选项**
 ```
 ```
	Mac$: git tag -a v1.4 -m 'my version 1.4'
	Mac$: ➜  git tag
		 TagRemotes.md
		 v1.4
 ```
 1.1: -m 选项指定了一条将会存储在标签中的信息
 通过使用 git show 命令可以看到标签信息与对应的提交信息：
 ```
	tag v1.4
	Tagger: jasperlee <281250541@qq.com>
	Date:   Thu Apr 21 13:10:24 2016 +0800

	my version 1.4

	commit 275ac4b0456baaa085066dc7c7695dd21185f8c7
	Author: jasperlee <281250541@qq.com>
	Date:   Wed Apr 20 11:39:47 2016 +0800

	    aaa

	diff --git a/TestGitColorUI.md b/TestGitColorUI.md
	index 2e85ca9..f577576 100644
	--- a/TestGitColorUI.md
	+++ b/TestGitColorUI.md
	@@ -1 +1,3 @@
	-# Test git diff color
	+# Test git diff color modify aaaa
	+
	+## add git color
	diff --git a/test.md b/test.md
	new file mode 100644
	index 0000000..e69de29	
 ```
 **输出显示了打标签者的信息、打标签的日期时间、附注信息，然后显示具体的提交信息。**

### 轻量标签
 2.1:  轻量标签本质上是将提交校验和存储到一个文件中 - 没有保存任何其他信息。 创建轻量标签，不需要使用 -a、-s 或 -m 选项，只需要提供标签名字：
 ```
	Mac$: git tag v1.4-lw
	Mac$: git tag
		➜  gitReference git:(dev) ✗ git tag
		TagRemotes.md
		v1.4
		v1.4-lw
 ```
 2.2: 这时，如果在标签上运行 git show，你不会看到额外的标签信息。 命令只会显示出提交信息：
 ```
	Mac$: git show v1.4-lw
		commit 275ac4b0456baaa085066dc7c7695dd21185f8c7
		Author: jasperlee <281250541@qq.com>
		Date:   Wed Apr 20 11:39:47 2016 +0800

		    aaa
 ```
### 后期打标签 
 1.1: 你也可以对过去的提交打标签。
 ```
	Mac$: git log --pretty=oneline
		9ad25c072be9f668e34ced867e2bb82ed143eee9 add content
		4d83b01310e50a339c639309f878180a67f9b4f2 modify README with jasper cmomit
		1568bf1ee30dc8ea1e35411791c6e74760b509a3 first commit
 ```
 1.2: 现在，假设在 v1.2 时你忘记给项目打标签，也就是在 “add content” 提交。 
      你可以在之后补上标签。 要在那个提交上打标签，你需要在命令的末尾指定提交的校验和（或部分校验和）:
 ```
	Mac$: git tag -a v1.2 9ad25c0
 ```
 ### 共享标签
 1.1 默认情况下，git push 命令并不会传送标签到远程仓库服务器上。 
     在创建完标签后你必须显式地推送标签到共享服务器上。 
     这个过程就像共享远程分支一样 - 你可以运行 git push origin [tagname]。
 ```
 	Mac$: git push origin v1.5
 ```
  1.2: 一次提交多个标签
 ```
        Mac$: git push origin --tags
 ```
 **现在，当其他人从仓库中克隆或拉取，他们也能得到你的那些标签。** 	

### 检出标签
 在 Git 中你并不能真的检出一个标签，因为它们并不能像分支一样来回移动。 
 如果你想要工作目录与仓库中特定的标签版本完全一样，
 可以使用 git checkout -b [branchname] [tagname] 在特定的标签上创建一个新分支：

 $ git checkout -b version2 v2.0.0
   Switched to a new branch 'version2'
 当然，如果在这之后又进行了一次提交，version2 分支会因为改动向前移动了，
 那么 version2 分支就会和 v2.0.0 标签稍微有些不同，这时就应该当心了。
