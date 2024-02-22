+++
title = 'Git Commit Rule'
date = 2024-02-16T18:24:16+09:00
draft = false
+++

This post will be an ever-evolving list of guidelines for personal projects to make my life easier. This rule will not be necessary for everyone.

### Initialization

``` shell
# When cloning a repo, make sure it is in the form
git clone https://username@github.com/username/repository.git
# This makes it easier to avoid accidental mixes of accounts when commiting, and managing multiple repositories with multiple accounts are easier.
```

### Tags to be used
``` shell
# Tag: (lowercase) short description of what you did
Init: start of project, skeleton code, boilerplate code
Feat: added a new feature
Doc: README.md or any other documentation related to the repository
Fix: fixed a bug
Refactor: refactored code
Test: added tests
Minor: some minor changes
```
