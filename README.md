# Git Cheat Sheet

### Git Basics

`git`

> to list some common Git commands

`git config --global user.name "John Doe"`

> set a name that is identifiable for credit when review version history

`git config --global user.email "johndoe@gmail.com"`

> set an email address that will be associated with each history marker

`git init`

> initialize an existing directory as a Git repository

`git clone [url]`

`git clone https://github.com/bradtraversy/proshop_mern`

> retrieve an entire repository from a hosted location via URL

`git status`

> show modified files in working directory, staged for your next commit

`git add [file]`

> add a file as it looks now to your next commit (stage)

`git add [file1] [file2] [file3]`

> add multiple files to staging area

`git add .`
`git add --all`

> add all files in the current repository to the staging area

`git reset [file]`

`git restore --staged [file]`

> remove file from the staging area, but leave the working directory unchanged. This unstages a file without overwriting any changes

`git commit -m "[descriptive message]"`

> commit your staged content as a new commit snapshot

`git commit -a`

> commit a snapshot of all changes in the working directory. This only includes modifications to tracked files (those that have been added with git add at some point in their history)

`git commit -am "[descriptive message]"`

> a power user shortcut command that combines the -a and -m options. This combination immediately creates a commit of all the staged changes and takes an inline commit message

`git log`

> show all commits in the current branch’s history

`git log --all`

> show all commits in the current branch’s history, even commits above the current HEAD when checkout to previous commits

`git branch [branch-name]`

> create a new branch at the current commit

`git branch`
`git branch --all`

> list your branches. a \* will appear next to the currently active branch

`git checkout [branch-name]`

> switch to another branch (or latest commit if in the same branch) and check it out into your working directory

`git checkout -b [new-branch]`

> to create a new branch & checkout

`git checkout [commitId]`

> switch to another commit (or any previous commits) and check it out into your working directory

`git branch -d [branch-name]`

> delete branch

`git merge [branch]`

> merge the specified branch's history into the current one (execute it from the branch we want to merge into)

`git merge feature`

> merge feature branch into the master branch (while staying on the master branch)

`git merge [commitId]`

> to merge selected commit into the current branch

`git diff`

> diff of what is changed but not staged

`git diff --staged`

> diff of what is staged but not yet committed

`git reset`

> reset staging area to match most recent commit, but leave the working directory unchanged

`git reset --hard`

> reset staging area and working directory to match most recent commit and overwrites all changes in the working directory

`git log --all --graph --decorate`

`git log --all --graph --oneline --decorate`

> the --graph option draws an ASCII graph representing the branch structure of the commit history. This is commonly used in conjunction with the --oneline and --decorate commands to make it easier to see which commit belongs to which branch

### Notes

`fast-forward merge:`

> A fast-forward merge can occur when there is a linear path from the current branch tip to the target branch. Instead of “actually” merging the branches, all Git has to do to integrate the histories is move (i.e., “fast forward”) the current branch tip up to the target branch tip

`3 way / recursive merge:`

> a fast-forward merge is not possible if the branches have diverged. When there is not a linear path to the target branch, Git has no choice but to combine them via a 3-way merge. 3-way merges use a dedicated commit to tie together the two histories

`merge conflicts:`

> Sometimes multiple developers may try to edit the same content. If Developer A tries to edit code that Developer B is editing a conflict may occur. To alleviate the occurrence of conflicts developers will work in separate isolated branches. The git merge command's primary responsibility is to combine separate branches and resolve any conflicting edits.

> When merge conflicts occurs, git responds "Automatic merge failed; fix conflicts and then commit the result". The output from git status indicates that there are unmerged paths due to a conflict. The most direct way to resolve a merge conflict is to edit the conflicted file. Once the file has been edited, add the file to staging and then commit with a descriptive message. Git will see that the conflict has been resolved and creates a new merge commit to finalize the merge

### Git Collaboration

> The git remote command is one piece of the broader system which is responsible for syncing changes. Records registered through the git remote command are used in conjunction with the git fetch, git push, and git pull commands

> The git remote command lets you create, view, and delete connections to other repositories. Remote connections are more like bookmarks rather than direct links into other repositories

`git remote add [alias] [url]`

> add a git URL as an alias

`git remote add origin https://github.com/brad/proshop_mern`

> create a new connection to a remote repository. After adding a remote, you’ll be able to use 'origin' as a convenient shortcut for URL in other Git commands

`git remote`

> list the remote connections you have to other repositories

`git remote -v`

> to view the URL(s)

`git push [alias] [branch]`

`git push origin master`

> transmit local branch commits to the remote repository branch

`git push -u origin master` OR

`git push origin master`
`git branch --set-upstream master origin/master`

> when you push to a remote and you use the --set-upstream flag git sets the branch you are pushing to as the remote tracking branch of the branch you are pushing

> adding a remote tracking branch means that git then knows what you want to do when you git fetch, git pull or git push in future. It assumes that you want to keep the local branch and the remote branch it is tracking in sync and does the appropriate thing to achieve this

`git pull`

> fetch and merge any commits from the tracking remote branch (fetch + merge = pull)

`git fetch [alias]`
`git fetch origin`

> fetch down all the branches from that Git remote

`git pull [alias]`
`git pull origin`

> fetch the specified remote’s copy of current branch and immediately merge it into the local copy

`git pull [alias] [branch-name]`

`git pull origin master`

> fetch the specified remote’s copy of specified branch and immediately merge it into the local copy

#### Additional

`git stash`

`git stash save "[descriptive message]"`

> stash the changes in a dirty working directory away. Use git stash when you want to record the current state of the working directory and the index, but want to go back to a clean working directory

`git stash -u`

> adding the -u option (or --include-untracked) tells git stash to also stash your untracked files

`git stash list`

> list stack-order of stashed file changes

`git stash pop`

> popping your stash removes the changes from your stash and reapplies them to your working copy

`git stash apply`

> alternatively, we can reapply the changes to our working copy and keep them in the stash

`git stash pop [stash-identifier]`

> by default, git stash pop will re-apply the most recently created stash: stash@{0}. You can choose which stash to re-apply by passing its identifier as the last argument

You can choose which stash to re-apply by passing its identifier as the last argument

`git stash drop`

> discard the changes from top of stash stack

`git stash clear`

> delete all stashes

`git reset --hard [commit]`

> clear staging area, rewrite working tree from specified commit

`git remote rm [alias]`

> Remove the connection to the remote repository called [alias]

`git remote rename [old-name] [new-name]`

> rename a remote connection from [old-name] to [new-name]
