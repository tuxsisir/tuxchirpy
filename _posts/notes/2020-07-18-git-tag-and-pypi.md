---
title: "Git Tags and Pypi"
date: 2020-07-18
draft: false
tags: ["git", "python", "pypi"]
---

### GIT Tags

`$ git tag -a 0.1 -m "Release v0.1"` # create tag

##### push tags to remote git server

`$ git push --tags`

##### view git tags
`$ git tag -n`

##### alternatively view git tags
`$ git log --oneline`

##### delete tag
`$ git tag -d <tag-name>`

### Make sure to update readme / screenshots / everything before tagging the release (pypi's perspective)

### Pypi:

##### install
`$ pip install --upgrade wheel pip install --upgrade setuptools`

##### remove existing builds

`$ rm -rf build/ dist/ nbprocusage.egg-info/`

##### build
`$ python setup.py sdist bdist_wheel`

##### upload via twine
`$ twine upload --repository testpypi dist/* --verbose`
