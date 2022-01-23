---
template: BlogPost
path: /svn-git-commands
date: 2021-03-02T00:00:00.000Z
title: "SVN commands and git equivalents"
summary: If you are moving from SVN to git, this should help you to find the equivalent commands in git
tags:
  - git
---

I am helping my company to move from SVN to GitHub, it's a big change for developers and this guide aims to make sense of different common commands:

## Status

Same as `svn status`, status will tell you about unstaged/staged changes you have.

```bash
git status
```

## Clone

Same as `svn checkout`, cloning a repository means you are obtaining a copy of the source code.

```bash
git clone https://github.com/UXnomaan/UXnomaan.git
```

## Pull/Fetch

Same as `svn update`, updates your local copy. Pull is used when you need to pull the latest on the branch you are on. Fetch is used to update everything (such as getting new branches locally)

```bash
git pull
# or
git fetch --all
```

## Add

Same as `svn add/commit`, you need to add/stage your change. svn add is used when a new file is added, or svn commit in case of an existing file. In git, there is tracked and untracked files. Git add will take care of new or existing files.

```bash
git add README.md
# or
git add .
#. means all the changes
```

## Commit

Same as `svn checkin`, you commit your changes. You are recording a revision when you commit your changes. Since git is a distributed version control system, you are committing/checking your changes to your local copy. Commits have a message where you specify what you have changed. Here’s an example of a commit

```bash
git commit -m "Changed README"
```

At this point, nobody in your team can see the changes. Next step is to push your changes.

## Push

No SVN equivalent since there is no concept of remote repository in SVN. After commits are pushed, they will show in GitHub.

```bash
git push
```

If you find yourself in a weird situation and wonder if there is a way to fix it, take a look at https://ohshitgit.com/
