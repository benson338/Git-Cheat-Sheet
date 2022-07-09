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
