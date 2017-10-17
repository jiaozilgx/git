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








