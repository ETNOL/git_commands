# Git

## What is version control?

Our first experience with version control usually starts with a file that we
want to update and circulate to others.

Our file:
report.xls

Becomes:
report_10/28/2015_EN.xls

This is the most basic version control. We now have a timestamp and initial to
version of our first file. We can hand if off to someone else and they can do
the same thing, creating a history of sorts.

The immediate problem that arises is when two people modify the file and we want
to combine the changes. This problem becomes exponentially more complicated as
more files, and more contributors are added.

## How Git solves this problem

Git provides software to support this versioning process. As files change,
versions can be saved from one change to the next. If the same file is changed
by two contributors, the changes are merged by git. If the changes potentially
conflict with each other, git raises attention to this conflict and aids in
resolving it.

Those are the key benefits of git but there are additional benefits as well. The
history of each file is saved, allowing a user to look at how a file got to a
certain state. A file can be reverted to a previous state, or a previous state
can be added back in to the current state. 

Also, a message is added, by the contributor, at each commit. This allows for
greater documentation as to why changes to a file were made.


## Some common terms

* Repository - A location where data is stored. In git, this is typically a
  plain folder.

## Getting Started

Start with an empty folder to act as your repository: 
mkdir my_git_repo
cd my_git_repo

Initialize your git source control:
git init

What just happened?
Git has setup a hidden folder in your repository. In this folder, git will
record all the data it needs to provide your source control. Most likely, you
will never need to interact with this folder directly.
However, git isn't tracking anything at this point. We haven't told it to do so
as of yet. So lets stage some files to track.

## Staging and Committing
The concept of staging files can be a bit tricky so lets first see it in action.
Start by making a file:
echo > README.md

Now lets see what git thinks of our new file in our repository:
git status


You'll see git report back that we have untracked files in our repo. Files can
be either tracked or untracked. Sometimes we may not want to track certain
files, but generally we track just about everything. Our next step is to stage
this file for a commit, but first, lets learn what a commit is.

### Commit
A commit in git is a snapshot of your repository at that point in time. As a git
repo progresses, its number of these snapshots can grow to thousands. Thats ok.
The whole purpose of git is to keep this detailed history of the repository. 

However, even though a commit is snapshot of the repo at a particular point, we
still have the option to control what that snapshot should include.  Lets make a
second file in our repo to demonstrate this control.

echo > MyFile.md

And again, what does git see:
git status

Right. So now git sees both of our files, untracked. Lets decide we want to make
our first snapshot(commit) only include our first file. To prepare it for this
commit, we stage the file:

git add README.md

And now our status:
git status

Ah, we now have a mix of untracked changes and staged changes ready for a
commit! Now we're ready to make that first commit in our repo:

git commit -m "initial commit"

The -m tells git that we want to add our commit message right now. Thats why we
follow it with our message "initial commit". Alternatively, if we leave that -m
off, git will open a text editor where we can type out our message. That editor
is often vi/vim, which can be a little frustrating for new users who aren't
comfortable with vi.  So for now, we'll do it the easy way.

Lets get a status to see whats going on now in our repo:
git status

We see our second file is still untracked, and the stage has been cleared as it
is now part of that first commit.
