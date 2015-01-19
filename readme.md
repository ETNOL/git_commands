#### add
Adds files to staging prior to a commit.  

Common use formats:
- git add (filename) { stages a single file }
- git add (folder) { stages a folder }
- git add --all { stages all files }
- git add *.(extension) {stages all files of a particular extension }

#### branch
A branch is a timeline. The main branch is refered to as the 'master'.

Common use formats:
- git branch (branch-name) { creates a new branch }
- git branch -d (branch-name) { deletes a branch, returning warning if uncommited changes exist }
- git branch -D (branch-name) { deletes a branch, overrides any uncommited warnings }
- git branch { lists local branches }
- git branch -a { lists all branches, local and remote }
- git branch -r { lists only remote branches }

#### checkout
Checkout changes working branches. Checkout also can be used to remove files from the staging area with the "--" option.

Common use formats:
- git checkout (branch) { changes current branch to branch entered }
- git checkout -b (branch) { creates new branch and changes it to current }
- git checkout -- (file) { removes a file from staging }

#### clone
Clone creates a local copy of a repository. After creating, it assigns fetch and pull remotes as well.
Common use formats:
- git clone (repository url) { creates a local copy of a remote repository in a new directory }
- git clone (repository url) (local repo name) { creates a local copy of a remote repo in a new directory and renames repo }

#### commit
Commit creates a entry in the timeline of a branch. Commit only retains files that have been staged prior to commiting.

Common use formats:
- git commit { submits commit, prompts for message through configured default text editor }
- git commit -m (message) { submits commit, shortcuts commit message }
- git commit -am (message) { adds all files, submits commit, shorcuts commit message }
- git commit --amend -m (message) { adds staged files to previous commit and updates previous commit message }

#### fetch
Fetch creates local branches of a repository from a remote location. Note that fetch does not merge these branches with the local master.

Common use formats:
- git fetch { updates local repository branch from configured 'fetch' branch }
- git fetch (remote name) (remote branch) { updates local repository branch from remote repository branch, creating new branch in process if one does not exist }

#### log
Log displays a historical database of commits.

Common use formats:
- git log { displays verbose format timeline }
- git log --pretty=oneline { displays less verbose format timeline }
- git log --graph { displays graphical representation of timeline }
- git log --graph --decorate --pretty=oneline --abbrev-commit --all { displays graphical representaion, with color, in less verbose format, with abbreviated commit messages, all commits together and terminates }

#### merge
Merge combines two branches into one. If a merge cannot be completed due to content conflicts a warning message will be displayed with the details. The affected file will also be updated with and indicator of the conflict(s) and the contents of both files conflicted section.

Common use formats:
- git merge (branch-name) { merges stated branch with currently active branch }

#### pull
Pull combines the features of fetch and merge into one command. Pulling from a remote repository will create a local copy of the branch and merge it into your downstream branch.

Common use formats:
- git pull { Performs fetch from 'fetch' remote and merges into current active branch }
- git pull -u (remote-name) (local-branch) { performs fetch from remote, merges into listed branch, and assigns remote to listed branch's 'fetch' remote }

#### push
Push sends your branch's commits upstream to your remote repository.

Common use formats:
- git push { pushes commits to configured push branch }
- git push -u (remote) (branch) { pushes stated branch commits to stated remote and assigns remote to stated branch's 'push' remote }
- git push (remote) (branch:remote branch) { pushes stated branch to remote as a different branch name }

#### reset
Reset moves the head of a branch backward. It can both "soft" reset, by removing the commit but keeping files in staging, or "hard" reset, by removing files from staging in addition to removing the commit.

Common use formats:
- git reset --soft HEAD^ { removes files from commit, leaving files staged }
- git reset --hard HEAD^ { removes commit entirely, unstaging files }

#### rm
Rm removes a file from your git repository and your file system. The removal does not complete until commited. It can also be used to remove tracking a file.

Common use formats:
- git rm (filename) { removes a file from repository }
- git rm --cached (file) { removes a file's tracked status from repository }

#### status
Status presents the current branch, staged files, and unstaged files.

Common use formats:
- git status { returns current branch status }
- git status -s { returns current branch file status in less verbose format } 
- git status -sb { returns current branch file status in less verbose format including branch status }

#### tags
Tags signify a specific commit that needs further reference. Tags are most commonly found to support versioning in a commit history.

Common use formats:
- git tag { lists tags used in repository }
- git checkout (tag) { moves head to commit associated with stated tag }
- git tag -a (tag name) -m (tag description) { adds a tag to current commit }
- git push --tags { pushes current state of tags to remote repository }

### remote
Used to interact with remote repositories. Precedes adding and removing remotes.

Common use formats:
- git remote { lists all remotes by name }
- git remote -v { lists all remotes in more verbose format, including 'fetch' and 'push' repositories }
- git remote add (remote-name)(remote url) { adds a new remote repository to local repository }
- git remote rm (remote-name) { removes a remote repository from local repostiory }
- git remote rename (old-remote-name) (new-remote-name) { renames a remote repository for local repository }
