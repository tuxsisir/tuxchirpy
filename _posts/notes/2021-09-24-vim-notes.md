---
title: "Vim"
date: 2021-09-24T17:21:09-07:00
draft: false
tags: ["vim"]
---


### Netrw

- `gn` to show current dir

### Telescope

Add to quickfix list

- Open telescope and mark files with `<C-Tab>`
- Make sure you are in **insert mode**.
- `<C-q>` to push and open in quickfix.
- `:cp` and `:cn` to navigate the list of quickfix.


### Vim Multiple Cursor

first search for the occurence...

/style

- go the first occurence

under the occurence, type cgn

and use the dot operator to continue on the next steps

###  Python linting using coc

#### Final Configuration:

- make sure that stuff is working by pylint apps/log/models.py
- pip install pylint && pip install pylint-common && pip install pylint-django


```json
{
    "python.linting.pylintArgs": ["--load-plugins", "pylint_django"]
}
```

---
- coc-settings (global) :CocConfig
```json
{
    "suggest.enablePreview": true,
    "diagnostic.displayByAle": true,
    "python.venvPath": "~/.virtualenvs/",
    "vetur.validation.template": true,
    "python.jediEnabled": true
}
```
---

- coc-settings (local) :CocLocalConfig
```json
{
  "python.pythonPath": "~/.virtualenvs/log-app/bin/python",
  "python.linting.pylintArgs": ["--rcfile", "~/.pylintrc"]
}
```
---

- vim ale settings
- we point empty to python

```vim

let g:ale_linters = {
            \   'javascript': ['eslint'],
            \   'python': [],
            \   'scss': ['scsslint']
            \ }

let g:ale_fixers = {
            \  'python': ['autopep8', 'yapf'],
            \  'javascript': ['eslint'],
            \  'vue': ['eslint']
            \}

```
---

- tried and failed

```
coc-config

{
    "python.venvPath": "~/.virtualenvs/",
    "python.jediEnabled": false,
    "python.linting.pep8Enabled": false,
    "python.linting.pylintEnabled": false,
    "vetur.validation.template": true,
    "diagnostic.displayByAle": true
}


{
  "python.pythonPath": "~/.virtualenvs/log-app/bin/python",
  "python.linting.enabled": false,
  "python.linting.pylintEnabled": true,
  "python.linting.pep8Enabled": true,
  "python.jediEnabled": true # by default true
}

# by default
"python.linting.enabled": true,
"python.linting.pylintEnabled": true,
"python.linting.pep8Enabled": false, # no need why use multiple when pylint helps it all
"python.linting.flake8Enabled": false, # no need why use multiple when pylint helps it all

```
---
- to generate rc file

`$ pylint --generate-rcfile`

vim using noconfig

`nvim -u NORC`

TODO:

Use Tmuxinator
(https://github.com/tmuxinator/tmuxinator)


netrw - create directory  (d)

netrw - create file (%)

---

### Links:

[Idiomatic Vimrc](https://github.com/romainl/idiomatic-vimrc)

---



vim move between matching tags

- 'Visual Mode' - V
- then, `a + t` to select whole block




---


- select text and indent ( fix it ) ( DONE )
- auto indent (with eslint ) (DONE)
- pep8 and pylint for linting python files (DONE)

DONE:
- TMUXP
- FZF



:Commits
:Glog — % [[ for current file changes ]]

VIM CODE  FOLDING

class User:
    —> za

fold ALL -  zM
fold indent - level wise: zm

open fold all -zR



---
#### IDEA VIM
---

H J K L

e - end of the word
b - beginning of the word
0 - beginning of the line
^ - first non-space character
$ - end of the line

Shift + H = HIGH
Shift + M = MIDDLE
Shift + L = LOW

Insert = i
Append / After = a

New Line Below = o
New Line Above = Shift + o

Delete

Delete Two Words = 2 d w
Delete Three Words = 3 d w

. [[ Period ]] = Repeat the last command

Delete the line = d d


Visual Mode [[ V ]]

aldsf alsdfj  lfoobar ljfoobar

Select the word and Change = c
Select the words and delete = x

Yank / Copy an Entire Line = y y
Yank / Copy = y
Paste = p

Search / Find / Filter

Search for the text = /
Find the next finding = n
Find the previous finding = Shift + N
find and replace with confirmation = %s/asdf/foobar/gc


foobar foobar sdfksdfkj akdsfjklfoobar


VIM CODE  FOLDING

class User:
    —> za

fold ALL -  zM
fold indent - level wise: zm

open fold all -zR

:Commits
:Glog — % [[ for current file changes ]]


netrw

gn to make the current treeptop
