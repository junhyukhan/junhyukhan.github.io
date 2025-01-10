+++
title = 'Git Commit Rule'
date = 2024-02-16T18:24:16+09:00
draft = false
tags = ['productivity']
+++

This post will be an ever-evolving list of guidelines for personal projects to make my life easier. This rule will not be necessary for everyone.

### Initialization
What we want is a parent folder, eg. `~/dev`, and all subdirectories to share git user information.

Use git's [includeIf](https://git-scm.com/docs/git-config#_conditional_includes) 
``` shell
# in the parent directory eg: ~/dev
# create a gitconfig file eg: ~/dev/.gitconfig_include
[user]
	email = youremail@domain.com
	name = Your Name
  # and other configs
```
Reference:
- [SO](https://stackoverflow.com/questions/21307793/set-git-config-values-for-all-child-folders)

{{< collapse summary="Old: Including the username when cloning a repo" >}}
This was used to designate repository-specific user name and emails.
This is not necessary if using the git's includeIf.
``` shell
# When cloning a repo, make sure it is in the form
git clone https://username@github.com/username/repository.git
# This makes it easier to avoid accidental mixes of accounts when commiting, and managing multiple repositories with multiple accounts are easier.
```
{{< /collapse >}}

### Tags to be used
I'll try to use the tags below, but as you can see from my commit history, it's all over the place... This list will be an ever changing list of tags that should be used.
``` shell
# Tag: (lowercase) short description of what you did
init: start of project, skeleton code, boilerplate code
create: created a file
update: updated a file
feat: added a new feature
doc: README.md or any other documentation related to the repository
fix: fixed a bug
refactor: refactored code
test: added tests
minor: some minor changes
```
