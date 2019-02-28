## Git
[Try](https://try.github.io/)

#### เริ่มต้น
- git init
- git remote add <name> <url>
```
git remote add  orgin https://github.com/laravel/laravel
```
- git add --all
- git commit -m "Init"
- git push origin
- git fetch origin
- git pull origin master

#### Merge
- เริ่มต้นด้วยการ ไปที่ branch หลัก (master)
- จากนั้นก็สั่ง git merge branch_name จาก branch ที่ต้องการ มาที่ master

#### Rebase
- git checkout <branch>
- git rebase master

#### Checkout
- by tag : git checkout tags/<tag_name>

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
- git branch -vv | grep 'origin/.*: gone]' | awk '{print $1}' | xargs git branch -d  

#### Stash
- git stash
- git stash pop
- git stash list ดูลิสทั้งหมด
- git stash clear -> clear all
- git stash drop stash@{0} -> drop by list

#### Remeber login
```
git config credential.helper store
```

#### Sub Module
- git submodule add <url> <dir>
```
git submodule add https://github.com/laravel/laravel app/laravel
```
- git submodule init
- git submodule update
-  
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

#### Git Workflow
- [link 1](https://medium.com/i-gear-geek/%E0%B8%A1%E0%B8%B2%E0%B8%97%E0%B8%B3%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%A3%E0%B8%B9%E0%B9%89%E0%B8%88%E0%B8%B1%E0%B8%81%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%81%E0%B8%B1%E0%B8%9A-git-workflows-%E0%B8%81%E0%B8%B1%E0%B8%99-e12609e9a8d2?fbclid=IwAR2klDGR6nZ1kvo44ArVWpPImxLMCamEHjcNwhEA_hv2JlQJQQnpUuzZHn0)
- [link 2](http://www.siamhtml.com/git-workflow-in-a-team/)

## Gitlab
#### git diff
![diff](/files/gitlabdiff.jpg "gitlab diff")

#### Learn more
- (https://devahoy.com/posts/git-cheat-sheet/)
- (http://anuchit-git.blogspot.com/2013/07/git.html)
