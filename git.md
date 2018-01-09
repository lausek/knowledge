# Commands

## Create local repo

    git init

## Create from existing repo

    git clone <url>

## Add file

    git add *

    # or for one file

    git add <file>

## Check current commit

    git status

## Commit changes

    git commit -m "<description>"

## Get changes from remote
    
    git pull

## Send changes to remote

    git push

## Add remote connection to existing repo
    
    git remote add origin <url>
    
    git config --global credential.helper cache

    git push --set-upstream origin master

## Create new branch

    git branch <branch> 

## Switch to branch

    git checkout <branch>
