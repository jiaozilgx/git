# git
学习——Git
一、配置
	git config --list 列出配置信息
	找到user.name,user.email两项
	git config --global user.name ''
	git config --global user.email ''
	注：此两条命令中去掉 --global 是什么情况

二、文件状态
	git status/git status -s 查看文件状态
	初始状态：
	On branch master 在主分支
		Your branch is up-to-date with 'origin/master'.  你的分支是从'origin/master'获取的最新的。
		
		nothing to commit, working tree clean 没有提交的东西，工作树干净
		
	空
	文件修改后：
	On branch master
		Your branch is up-to-date with 'origin/master'.

		Changes not staged for commit: 更改但没有用于提交
		  (use "git add <file>..." to update what will be committed)
		  (use "git checkout -- <file>..." to discard changes in working directory)

				(修改的)modified:   README.md(红色)

		no changes added to commit (use "git add" and/or "git commit -a")
	
	M README.md(红色)
	文件加入暂存区后：
	On branch master
		Your branch is up-to-date with 'origin/master'.

		Changes to be committed: 修改提交
		  (use "git reset HEAD <file>..." to unstage)

				modified:   README.md(绿色)
	
	M  README.md(绿色)
	文件由暂存区提交到库中：
	On branch master
		Your branch is ahead of 'origin/master' by 1 commit. 
		你的分支相比以前的''origin/master'多了1此提交。
		  (use "git push" to publish your local commits)

		nothing to commit, working tree clean

	空
	新建文件后：
	On branch master
		Your branch is ahead of 'origin/master' by 4 commits.
		  (use "git push" to publish your local commits)

		Untracked files: 未跟踪的文件
		  (use "git add <file>..." to include in what will be committed)

				sss.txt

		nothing added to commit but untracked files present (use "git add" to track)
	
	?? sss.txt
	新文件加入暂存区后：
	On branch master
		Your branch is ahead of 'origin/master' by 4 commits.
		  (use "git push" to publish your local commits)

		Changes to be committed:
		  (use "git reset HEAD <file>..." to unstage)

				modified:   README.md
				new file:   sss.txt

	A  sss.txt

三、查看提交历史
	git log
	git log --pretty=oneline 以一行的形式显示
		28a3fc865bb145d2c051a291c4016c6a4dbca699 (HEAD -> master) 20
		3b05aa1ccd66065686301c99a08cceb94ac075ea 19
		332eb6f08ec9a5508b69a4ccfa3d17075051e848 18
		caae3e60b7ca976dc40518765c651cc6d3581367 17
		8d1ebcf618b8847861521a3547f66cbbaa58c1a3 17/10/17 23:28
		34241fe2ae3caa704702b34767be9e40e295ae78 (origin/master, origin/HEAD) 17/10/15
		5f50d595729dcfbfcc0f3a3c599543aee4435b14 Initial commit
	
	git reset --hard HEAD^ 退回到上个版本
	git reset --hard 版本号 退回到指定版本

	git reflog 记录了每条命令，即历史命令

四、查看区别
	工作区、版本区（暂存区、分支）
	git diff HEAD -- README.md 工作区与版本库最新版本的区别
	git diff 查看当前文件与暂存区中文件的差异
	git diff --staged/cached  查看暂存区文件与已提交文件之间的差异

五、撤销修改
	git checkout -- file 丢弃工作区的修改
	两种情况：
		1.修改的已加入暂存区后再修改
			退回到加入暂存区的状态
		2.修改的没加入暂存区
			退回到工作区clean的状态
	git reset HEAD file 把暂存区的撤销

六、删除文件
	git rm file 从版本库中彻底删除文件
	注：若没有在版本库中删除文件，可以用 git checkout -- file 来恢复

七、上传到远程版本库
	git remote add origin git@github.com:jiaozilgx/git.git
	将本地仓库与远程的连接
	git push -u origin master 首次推送
	git push origin master 以后推送

八、分支
	git branch dev 创建分支dev
	git checkout dev 切换到分支dev
	git checkout -b dev 上两条命令的合并
	
	git branch 查看当前分支

	git branch dev 合并dev分支到当前分支

	git branch -d dev 删除dev分支

九、冲突
	对于多个分支，每个分支都有各自的修改，在合并的时候就会产生冲突
	解决方式：git status 查看两个分支提交的各自差异
			  手动将差异修改
			  再合并分支

		  再合并dev分支
	git log --graph 查看分支合并图

十、合并分支
	默认模式 Fast forward模式
	禁用Fast forward模式



















	


