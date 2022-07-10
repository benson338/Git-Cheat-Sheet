# Git Cheat Sheet

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

`git add .`
`git add --all`

> add all files in the current repository to the staging area

`git commit -m "[descriptive message]"`

> commit your staged content as a new commit snapshot

`git log`

> show all commits in the current branch’s history

`git checkout [commitid]`

> switch to another commit (or any previous commits) and check it out into your working directory

`git log --all`

> show all commits in the current branch’s history, even commits above the current HEAD when checkout to previous commits

`git branch [branch-name]`

> create a new branch at the current commit

`git branch`

> list your branches. a \* will appear next to the currently active branch

`git checkout [branch-name]`

> switch to another branch (or latest commit if in the same branch) and check it out into your working directory

`git checkout -b [new-branch]`

> to create a new branch & checkout

`git merge [branch]`

> merge the specified branch's history into the current one (execute it from the branch we want to merge into)

`git merge feature`

> merge feature branch into the master branch (while staying on the master branch)

`git diff`

> diff of what is changed but not staged

`git diff --staged`

> diff of what is staged but not yet committed

`git stash`

> stash the changes in a dirty working directory away. Use git stash when you want to record the current state of the working directory and the index, but want to go back to a clean working directory

`git stash list`

> list stack-order of stashed file changes

`git stash pop`

> write working from top of stash stack

`git stash drop`

> discard the changes from top of stash stack

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

...
