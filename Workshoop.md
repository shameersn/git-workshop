# Git Workshop

## Configure Git

1. List git configuaration - `git config --list` `git --version`

2. Configure Git Glogaly - dislplaying in commit messages

```bash
  git config --global user.name "Your Name"
  git config --global user.email you@example.com
```

## Init a Git project

1. Init a folder a git project - `git init` (creat a .git folder and start tracking the files inside that folder)

## Git Ignore

1. can use `.gitignore` tells git which files (or patterns) it should ignore.
2. [Gitignore.io](https://gitignore.io/)
3. `/*.cmake /*.DS_Store /.user /build` sample

## Git concepts

Untracked files
New files that Git has not been told to track previously.

Working area
Files that have been modified but are not committed.

Staging area
Modified files that have been marked to go in the next commit.

## Common git commands in a day-to-day workflow

`git status`
`git log` `--oneline` - list commit logs
`git fetch` git fetch really only downloads new data from a remote repository - but it doesn't integrate any of this new data into your working files. Fetch is great for getting a fresh view on all the things that happened in a remote repository

`git pull origin branch_name` - download the changes from branch and merge (common usecase - can be used to combine two branches)

`git push branch_name remote_name`

`git merge branch_name` (Join two or more development histories together, common usecase - can be used to combine two branches)
`git merge --abort` can only be run after the merge has resulted in conflicts. `git merge --abort` will abort the merge process and try to reconstruct the pre-merge state
`git merge --continue` can only be run after the merge has resulted in conflicts. helps to complete the merge

```bash
<<<<<<< HEAD(master)
conflicted text from HEAD(master)
=======
conflicted text from hotfix
>>>>>>> hotfix
```

`git merge --squash` This will take all the commits from the bugfix branch, squash them into 1 commit, and merge it with your master branch.

abort a merge - `git reset --merge ORIG_HEAD` or `git reset --hard ORIG_HEAD` or `git reset --hard commit_sha`

git log shows the commit log accessible from the refs (heads, tags, remotes)
git reflog is a record of all commits that are or were referenced in your repo at any time.

## Create a repo - Github

1. SSH `git remote add origin git@github.com:shameersn/git-demo.git`
2. HTTPS `git remote add origin https://github.com/user/repo.git`

## Committing

Is it possible to add and commit an empty directory to git -
Create an empty file called .gitkeep in the directory, and add that.

```bash
git status
git diff
git add filename || --all || .
git commit -m 'My change'
git push origin master
git log
```

## Feature branching

1. Efficient parallel workflow for teams.
2. Develop each feature in a branch.
3. Keeps changes isolated.

## Pull requests

1. Use github to create pr
2. [Creating a pull request](https://help.github.com/en/articles/creating-a-pull-request)
3. [How to write the perfect pull request](https://github.blog/2015-01-21-how-to-write-the-perfect-pull-request/)
