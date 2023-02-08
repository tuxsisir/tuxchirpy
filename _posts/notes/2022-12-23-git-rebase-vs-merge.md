---
title: Understanding Git Rebase vs Merge
date: 2022-12-23
tags: ["git"]
pin: false
category: vcs
image: https://source.unsplash.com/EUzk9BIEq6M/800x300
---

In this post, we will quickly go through `git rebase` and `git merge` as simply as possible.

### Git rebase vs merge
Both rebase and merge are tools in git which integrates changes from one branch to another. They integrate work splitted in two different branch.

### Let's create a STORY around it
- Meet (MIKE) who is maintaining the project and working as a Senior Developer who is overviewing / reviewing new contributions / maintaining the project.
- Now, (JOHN) is a guy who is working in the project recently and starting to work on this new feature of `seo`.

```console

** Hi I am John, it's a normal day in my office today and starting my day
with new branch.

$ git checkout -B feature-seo (checks out to new branch from main)

(starts working ...)

$ git commit -m "WIP: Fix meta tags"

(carries on with their progress ...)
==============================================================================


** MEANWHILE, Mike fixes this crucial BUG and pushes to main which everyone should
"merge" asap on their branch and continue their work.

```

Quick Update by now:

- John is in middle of something.
- Mike is asking all the other team members to sync their repo with main.

- John has two options to integrate the work:
  - `$ git merge main`
  - `$ git rebase main`

- Both commands will pull Mike's recent changes from main to John's working branch.


### Git Merge
Git merge will bring the changes by introducing a new commit as a **"Merge branch <main> into ..."** in the branch's history. This option will preserve the history of each and every merge.
If the main branch is quite busy then it can pollute the history too.


### Git Rebase
Note the recent commit of John _(WIP: Fix meta tags)_ on his working branch. Now if John picks the rebase option
to merge the work from main branch, what rebase does is, it stacks the commit from main on top of John's recent commit _(WIP: Fix meta tags)_ and
forms this linear clean history on top of target branch (main) in our case.

### Which option should John pick?
This entirely depends on how their team workflow is based on. Git merge is more straightforward, preserves each merge history and mostly used while git rebase
if handled well brings more cleaner and linear history.

Thanks for reading folks.
