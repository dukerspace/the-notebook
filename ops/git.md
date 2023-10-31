---
id: git
title: Git
type: docs
path: the-notebook/ops/git
---

#### เริ่มต้น

- git init
- git remote add <name> <url>

```
git remote add  orgin https://github.com/laravel/laravel
```
- git add .
- git add --all
- git commit -m "Init"
- git push
- git commit -am "msg" (-a to automatically stage all changes)
- git fetch origin
- git pull origin master

#### Message

- test
    สร้างหรือเปลี่ยนแปลง Test Code
- feat
 เพิ่ม Feature ใหม่ สำหรับ Project
- refactor
    ทำ Code Refactoring โดยไม่กระทบกับ Logic หรือ Rules
- style
    เมื่อมีการเปลี่ยน Code Style หรือมีการ Formatting Code
- fix
    แก้ Error หรือ Bugs ในระบบ
- docs
    เปลี่ยนแปลง Document ของ Project
- chore
    มีการเปลี่ยนแปลงที่ไม่เกี่ยวกับ Code หรือ Test เป็นการเปลี่ยนแปลงด้าน Development Dependency หรือ Tools เช่น eslint, prettier, .gitignore
- build
    มีการเปลี่ยนแปลงที่ส่งผลต่อ Build Process หรือ External Dependency
    เปลี่ยนแปลง Dependency ของ Project
- perf
    การเปลี่ยนแปลงที่เกี่ยวข้องกับการเพิ่ม Performance ของระบบ
- ci
    เปลี่ยนแปลง CI/CD Configuration File เช่น Circle ,Travis, Jenkins
- revert
    มีการย้อยกลับไปที่ Commit ก่อนหน้านี้

#### Merge

- เริ่มต้นด้วยการ ไปที่ branch หลัก (master)
- จากนั้นก็สั่ง git merge branch_name จาก branch ที่ต้องการ มาที่ master

#### Pull

git pull master to develop branch
git pull <remote> <master-branch> <develop-branch>

```
git pull origin master develop
```

#### Rename branch
git branch -m <new-branch-name>
```
git branch -m main
```

#### Rebase

- git rebase develop
- git merge bugFIx  
- git pull --rebase
- git rebase --continue

#### Tag checkout

```
git checkout tags/<tag_name>
```

#### Tag add

```
git tag <tagname>
```

### Tag list

```
git tag -l
```

#### Tag push

```
git push --tag
```

#### Tag pull
```
git pull --tags
```

#### Tag delete

- delete tag in host

```
git push --delete origin tagname
```

- delete tag in local

```
git tag --delete tagname
```

#### Update remote url

```
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git (https://help.github.com/articles/changing-a-remote-s-url/)
```

#### Delete local branch

- git branch -D branch_name
- git branch | grep 'bug-\.' | xargs git branch -d (ลบชื่อเหมือน)

#### Delete remote branch

- git push <remote_name> --delete <branch_name>

```
git push origin --delete develop
```

#### Delete local does note exist remote

```
git remote prune origin
```

- git branch -vv | grep 'origin/.\*: gone]' | awk '{print $1}' | xargs git branch -d

#### Stash

- git stash
- git stash pop
- git stash list ดูลิสทั้งหมด
- git stash clear -> clear all
- git stash drop stash@{0} -> drop by list

#### Reset new file and folder

```
git clean -fd
git clean -f
git clean -n => -n ก็คือ dry-run ยังไม่ได้ run กันจริง ๆ แ
```

#### reset file

git checkout -- <file_name>

```
git checkout -- git.md
```

#### Remeber login

```
git config credential.helper store
```

#### move same file name

```
git mv -f {old_file} {new_file}
```

#### multiple account

- [link](https://www.freecodecamp.org/news/manage-multiple-github-accounts-the-ssh-way-2dadc30ccaca/)

#### Sub Module

- git submodule init
- git submodule add <url> <dir>

```
git submodule add https://github.com/laravel/laravel app/laravel
```

- Git Pull with Submodule

```
git submodule update --init --recursive
```

- Update submodules

```
git submodule update --recursive --remote
```

##### Delete Sub module

1. ลบข้อมูล .gitmodules
2. ลบข้อมูลใน sumoudle entry ใน .git/config
3. git rm --cached <folder>

```
git rm -cached app/laravel
```

##### Easy way

- git sumodule update --init

```
git config --global alias.update '!git pull && git submodule update --init --recursive'
```

```
git config --global alias.pullall '!f(){ git pull "$@" && git submodule update --init --recursive; }; f'
```

#### Worktree

- จัดการกับโค้ดโครงการเดียว แต่มีก๊อบปี้หลายชุด
- ไม่ควรใช้กับโครงการที่มี submodule โดยเด็ดขาด
- git worktree add -b <new_branch> <directory> <old_branch>

```
git worktree add -b hotfix hotfix develop
```

- git worktree add <directory> <branch>

```
git worktree add  ../new_branch develop
```

- clean

```
git worktree prune
```

#### Check repo size

```
git gc
git count-objects -vH
```

#### Git alias

```

```

#### [Git Workflow](../theory/git-workflow.md)

## Gitlab

#### git diff

![diff](/files/gitlabdiff.jpg "gitlab diff")

#### Learn more

- (https://devahoy.com/posts/git-cheat-sheet/)
- (http://anuchit-git.blogspot.com/2013/07/git.html)
- [Try](https://try.github.io/)
