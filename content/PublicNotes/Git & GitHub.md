---
title: Git & GitHub
tags: Public
Aliases:
Date created: 2024-03-01 21:25
---
Git commands I forget too often

### Actions
[[GitHub Actions]]

### Repositories

#### Add Local Repo to GitHub
`git remote add <name> <remote url>`

#### Remove Directory from Repository, not Local
`git rm -r --cached <name> `

#### Merging Unrelated Histories
`git pull  --allow-unrelated-histories`

### Branches
#### Update a Feature Branch to Main Current State
`git merge <main branch>` on the feature branch
#### Set Branch Tracking
`git branch -u <remote>/<branch>`
#### Auto Branch Tracking
`git config --global push.autoSetupRemote true`
#### Rename Branch
`git branch -m <new name>`

#### Delete Branch
`git branch -d <branch-name>`
#### Move Uncommitted Changes to a New Branch
`git switch -c <new-branch>`
#### Move Uncommitted Changes to an Existing Branch
`git switch -c <new-branch>`
#### Get All Changes from Another Branch
```bash
git checkout clean_branch
git merge --squash changed_branch
```
#### Create Local Branch from Remote Branch
`git checkout -b <new_branch_name> <remote_name>/<remote_branch_name>`

#### Move Branch to Start at Current Master State
`git rebase master` (on feature branch)

### Commits
#### Remove File from Commit
`git reset <file>`

#### See Commit History
`git log --pretty=oneline`

### Repository Configuration

repository configuration is stored in a `.gitattributes` file in the repository root

#### Disable Auto Setting CRLF
```bash
git config --global core.autocrlf false
```
#### Change Repository Eol to LF
`<files> <type> eol=<encoding>`
`*.py text eol=lf`

