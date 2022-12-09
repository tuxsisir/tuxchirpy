---
title: "Git Cheatsheet"
date: 2020-07-14
draft: false
tags: ["git"]
---

### git checkout with remote branch updates
```sh
$ git remote update
$ git fetch
$ git checkout --track origin/<BRANCH-NAME>
```

### delete remote branch
```sh
$ git push <remote_name> --delete <branch_name>
```

### git untrack file or a folder

```sh
$ git rm -r --cached path_to_your_folder/
```

### rename branch git
https://multiplestates.wordpress.com/2015/02/05/rename-a-local-and-remote-branch-in-git/

### GIT FLOW
https://danielkummer.github.io/git-flow-cheatsheet/
