---
id: shell
title: Shell Script
type: docs
path: the-notebook/lang/shell
---

### Shell Script

- set -e will cause the script to exit on any error/non-zero return value.
- set +e (the default) errors will occur, but the script will continue to run.

### import .env
. <file>
```
. .env
```


### ssh login with private key
ssh -i ./path/key  root@localhost
```
ssh -i ./private.key root@localhosts
```