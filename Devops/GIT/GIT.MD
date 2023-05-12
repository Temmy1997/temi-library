# GIT

Git is a free open source verion control system

## Version control

This is a way we programmers track our code changes.
We bsically save the initial verion of our code in GIT and when we update the code we can save it into GIT again.
As our code continues to change we can look back at all the changes we have made in our code.

NOTE:
This version contol helps us to check what we change in our code, track done bugs, and go back to a previoud verion of code.

* Repository: This is basically a folder where my project is kept.

Note: Different between GIT and GITHUB

1. Github is basically a website that host all repository.

## GIT COMMANDS

* clone => Brings a repository that is on Github into a folder in my local machine.
* add => Track all the changes in GIT.
* commit => SAVE all the changes I made in Git.
* push => Once I have made the changes locally on my computer, this command uploads the file to Github.
* pull => Download changes to my local computer from Github.
* git init : initialize local repo
* git remote add : add a new repository
* git clone: to clone an existing repo

# Flow of pushing local files and folder changes to remote repo

- git add `<all-changes>`: This is to track all changes
- git commit -m "`<description>`"
- git push -u origin `<current-local-branch>`
- always run git status to check current status of your git repo
- git checkout -b `<new-branch-name>` `<current-branch-you-are-checking-off-from>`: create new branch off another updated branch
- git checkout "branch-name"(SWITCH INTO A BRANCH)
