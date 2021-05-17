---
title: Other FAQ
nav_order: 5
layout: default
parent: Operation
---
### How do you upgrade your node?

### How do you switch to a Pull Request for testing

This would fetch a pull request (in this case 246) into a branch
we'll call telegram and change to it

```bash
git fetch origin pull/246/head:telegram
git checkout telegram
```

To refresh, if the pull-request is updated, you must switch back to
a standard branch, then you can repeat the commands above

```bash
git checkout develop
git fetch origin pull/246/head:telegram
git checkout telegram
```
