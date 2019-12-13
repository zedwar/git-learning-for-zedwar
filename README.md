# git-learning-for-zedwar
A light learning for github
git 
1.cd pwd
2.ls ll
3.touch new.md
4.rm new.md
5.mkdir new
6.rm new -r
  	9）、mv 移动文件, mv index.html src index.html 是我们要移动的文件, src 是目标文件夹,当然, 这样写,必须保证文件和目标文件夹在同一目录下。
	10）、reset 重新初始化终端/清屏。
	11）、clear 清屏。
	12）、history 查看命令历史。
7.git config -l 
8.#查看系统config
	git status [filename]
#查看所有文件状态
	git status
# 添加指定文件到暂存区
	$ git add [file1] [file2] ...
# 添加指定目录到暂存区，包括子目录
	$ git add [dir]
# 添加当前目录的所有文件到暂存区
	$ git add .
#直接从暂存区删除文件，工作区则不做出改变
	git rm --cached <file>
#直接从暂存区删除文件，工作区则不做出改变
	git rm --cached <file>
#如果已经用add 命令把文件加入stage了，就先需要从stage中撤销
	git reset HEAD <file>...
#移除所有未跟踪文件
#一般会加上参数-df，-d表示包含目录，-f表示强制清除。
	git clean [options] 
#只从stage中删除，保留物理文件
	git rm --cached readme.txt 

#不但从stage中删除，同时删除物理文件
	git rm readme.txt 

#把a.txt改名为b.txt
	git mv a.txt b.txt 
#查看文件修改后的差异
	git diff [files]
#比较暂存区的文件与之前已经提交过的文件
	git diff --cached
#比较repo与工作空间中的文件差异
	git diff HEAD~n
#用法一
git checkout [-q] [<commit>] [--] <paths>...
#用法二
git checkout [<branch>]
#用法三
git checkout [-m] [[-b]--orphan] <new_branch>] [<start_point>]
$ git checkout branch
#检出branch分支。要完成图中的三个步骤，更新HEAD以指向branch分支，以及用branch  指向的树更新暂存区和工作区。

$ git checkout
#汇总显示工作区、暂存区与HEAD的差异。

$ git checkout HEAD
#同上

$ git checkout -- filename
#用暂存区中filename文件来覆盖工作区中的filename文件。相当于取消自上次执行git add filename以来（如果执行过）的本地修改。

$ git checkout branch -- filename
#维持HEAD的指向不变。用branch所指向的提交中filename替换暂存区和工作区中相   应的文件。注意会将暂存区和工作区中的filename文件直接覆盖。

$ git checkout -- . 或写作 git checkout .
#注意git checkout 命令后的参数为一个点（“.”）。这条命令最危险！会取消所有本地的  #修改（相对于暂存区）。相当于用暂存区的所有文件直接覆盖本地文件，不给用户任何确认的机会！

$ git checkout commit_id -- file_name
#如果不加commit_id，那么git checkout -- file_name 表示恢复文件到本地版本库中最新的状态

# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]

# 提交工作区自上次commit之后的变化，直接到仓库区，跳过了add,对新文件无效
$ git commit -a

# 提交时显示所有diff信息
$ git commit -v

# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
$ git commit --amend -m [message]

# 重做上一次commit，并包括指定文件的新变化
$ git commit --amend [file1] [file2] ...
#修订提交
git commit --amend
#撤销上一次的提交
git reset --hard HEAD~1