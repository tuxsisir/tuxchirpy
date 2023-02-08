---
title: "Github Action to push to another repository - Usage and Example"
date: 2022-12-24
tags: [github, git]
categories: [programming]
image: https://source.unsplash.com/VPOJgMLFYzw/800x300
pin: true
---

In this walkthrough, we will push the changes made on one github repo to another repo using github action - [github-action-push-to-another-repository](https://github.com/cpina/github-action-push-to-another-repository).

### Here's the Use Case

> Let us suppose that there are two similar repositories and we would want to share code to parent repo from any another branched repo without disclosing the parent repo. This makes good sense when there is a new developer who needs to be introduced to the repo but the owner of the repo does not want to
share all the details of the repo initially.
{: .prompt-tip }

Let's start with this case scenario.

![github-action-push-to-another-repository](/assets/img/posts/github-action-push-to-another.png)

### Few things to take note of:
- Repo A
  - Repo A is a parent repo where Dev. A and Dev. B are working since Mesozoic era.
  - It is the main parent repo where we would want to push the code from Repo B.
- Repo B
  - This repo is the splitted repo from Repo A where owner of the Repo A would like to strip features and provide this repo to new developer without disclosing what Repo A is all about.

- Final Working Github Action Yaml

{% raw %}
```yaml
name: CI

on:
  push:
    branches: [ dev ]
  pull_request:
    branches: [ dev ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Push pages
        id: push_pages
        uses: cpina/github-action-push-to-another-repository@ssh-deploy-key
        env:
          SSH_DEPLOY_KEY: ${{ secrets.SSH_DEPLOY_KEY }}
          GH_USERNAME: ${{ secrets.GH_USERNAME }}
          USER_EMAIL: ${{ secrets.USER_EMAIL }}
          DESTINATION_REPO_NAME: ${{ secrets.DESTINATION_REPO_NAME }}
        with:
          source-directory: 'pages'
          destination-github-username: '${{ secrets.GH_USERNAME }}'
          destination-repository-name: '${{ secrets.DESTINATION_REPO_NAME }}'
          user-email: ${{ secrets.USER_EMAIL }}
          commit-message: See ORIGIN_COMMIT from $GITHUB_REF
          target-branch: dev
          target-directory: 'pages/dashboard'
      - name: Push assets
        id: push_assets
        uses: cpina/github-action-push-to-another-repository@ssh-deploy-key
        env:
          SSH_DEPLOY_KEY: ${{ secrets.SSH_DEPLOY_KEY }}
          GH_USERNAME: ${{ secrets.GH_USERNAME }}
          USER_EMAIL: ${{ secrets.USER_EMAIL }}
          DESTINATION_REPO_NAME: ${{ secrets.DESTINATION_REPO_NAME }}
        with:
          source-directory: 'assets'
          destination-github-username: '${{ secrets.GH_USERNAME }}'
          destination-repository-name: '${{ secrets.DESTINATION_REPO_NAME }}'
          user-email: ${{ secrets.USER_EMAIL }}
          commit-message: See ORIGIN_COMMIT from $GITHUB_REF
          target-branch: dev
          target-directory: 'assets/'
      - name: Test changes move from test-push to test-pull
        run: echo $DESTINATION_CLONED_DIRECTORY
```
{% endraw %}

> Note: We are using github action [cpina/github-action-push-to-another-repository](https://github.com/cpina/github-action-push-to-another-repository) to push the changes. If you need further exploration follow the link for more detailed documentation.
{: .prompt-info }

### Breaking down YAML action configuration

When to execute the action?

```yaml
name: CI

on:
  push:
    branches: [ dev ]
  pull_request:
    branches: [ dev ]

```
How are we executing the action?
- Either using ssh-deploy-key
- Or, GitHub Access Token

- Each name record can be configured to push directory or file
- Here, we are pushing `pages/` directory, if you see complete yaml we are pushing `pages/` and `assets/` directories to the Repo A

{% raw %}
```yaml
      - name: Push pages
        id: push_pages
        uses: cpina/github-action-push-to-another-repository@ssh-deploy-key
        env:
          SSH_DEPLOY_KEY: ${{ secrets.SSH_DEPLOY_KEY }}
          GH_USERNAME: ${{ secrets.GH_USERNAME }}
          USER_EMAIL: ${{ secrets.USER_EMAIL }}
          DESTINATION_REPO_NAME: ${{ secrets.DESTINATION_REPO_NAME }}
        with:
          source-directory: 'pages'
          destination-github-username: '${{ secrets.GH_USERNAME }}'
          destination-repository-name: '${{ secrets.DESTINATION_REPO_NAME }}'
          user-email: ${{ secrets.USER_EMAIL }} # Email of the commit author
          commit-message: See ORIGIN_COMMIT from $GITHUB_REF
          target-branch: dev # To which branch we are sending the commits to
          target-directory: 'pages/dashboard' # Make sure this repository exists on the parent repo
```
{% endraw %}


### Example: Here's the working github repo that mimics above mentioned repos

| Repo A                                                                                                                                                                                        | Repo B                                                                      |
| :----------------------------------------------------------------------------                                                                                                                 | :-------------------------------------------------------------------------- |
| [try-pull-another-repo](https://github.com/tuxsisir/try-pull-another-repo)                                                                                                                    | [try-push-another-repo](https://github.com/tuxsisir/try-push-another-repo)  |
| -                                                                                                                                                                                             | This is where we keep github yaml workflow                                  |
| -                                                                                                                                                                                             | `.github/workflows/` exists here                                            |
| Dev A. and Dev B. are working here                                                                                                                                                            | New Dev is working here                                                     |
| Note: To make any changes on these shared directories Dev A. and Dev B.<br> must work on Repo B and contribute from there, <br>because each time the code is pushed, target directories are wiped |                                                                             |
|                                                                                                                                                                                               |                                                                             |
