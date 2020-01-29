---
id: shell
title: Shell Script
type: docs
path: the-notebook/lang/schell
---

### Shell Script

- set -e will cause the script to exit on any error/non-zero return value.
- set +e (the default) errors will occur, but the script will continue to run.

### import .env
. <file>
```
. .env
```