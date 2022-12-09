---
title: "Adding multiple Github Accounts"
date: 2022-05-09
draft: false
tags: ["git"]
---

Configure the following things:

Go to your .ssh

`$ <editor> $HOME/.ssh`

Essentially, Link your keys to different accounts on your config.

###### How to create a new key?

`$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
where rsa is the key type...


`$ <editor> $HOME/.ssh/config`

```Bash
Host github.com-tuxwork
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_tuxwork # your work key name
   IdentitiesOnly yes

Host github.com-tuxpersonal
  Hostname github.com
  User git
  IdentityFile ~/.ssh/id_tuxpersonal # your personal key name
  IdentitiesOnly yes
```

###### Make sure to add your newly created key
`ssh-add $HOME/.ssh/id_rsa` (<id_rsa> is your your newly created key)

###### Update your repos

Now go to your repo, make sure your repos are hyphenated as mentioned in the config.

`$ cd <your_repo>`

`$ git config --local -e`

```Bash
...
...
[remote "origin"]
        url = git@github.com-tuxpersonal:tuxsisir/tuxsisir.github.io.git
        fetch = +refs/heads/*:refs/remotes/origin/*
```

Update url to github.com-tuxpersonal (hyphenated) as mentioned in the config.

References:

[Handling Multiple Github Accounts on MacOS](https://gist.github.com/Jonalogy/54091c98946cfe4f8cdab2bea79430f9)