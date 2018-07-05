## Git
[Try](https://try.github.io/)

#### เริ่มต้น
- git init
- git remote add origin http://github.com/??
- git add --all
- git commit -m "Init"
- git push origin

#### Sub Module
- git config --global alias.pullall '!f(){ git pull "$@" && git submodule update --init --recursive; }; f'

#### Pull
- git pull origin master

#### Fetch
- git fetch origin

#### Merge
- เริ่มต้นด้วยการ ไปที่ branch หลัก (master)
- จากนั้นก็สั่ง git merge branch_name จาก branch ที่ต้องการ มาที่ master

#### Rebase
- git checkout <branch>
- git rebase master

#### Checkout
- by tag : git checkout tags/<tag_name>

#### Update remote url
- git remote set-url origin https://github.com/USERNAME/REPOSITORY.git (https://help.github.com/articles/changing-a-remote-s-url/)

#### Delete local branch
- git branch -D branch_name
- git branch | grep 'bug-\.' | xargs git branch -d (ลบชื่อเหมือน)

#### Delete remote branch
- git push <remote_name> --delete <branch_name>

#### Delete local does note exist remote
- git remote prune origin  
- git branch -vv | grep 'origin/.*: gone]' | awk '{print $1}' | xargs git branch -d  

#### Remeber login
- git config credential.helper store

## Gitlab
#### git diff
![diff](/files/gitlabdiff.jpg "gitlab diff")

#### Learn more
- (http://www.siamhtml.com/git-workflow-in-a-team/)
- (https://devahoy.com/posts/git-cheat-sheet/)
- (http://anuchit-git.blogspot.com/2013/07/git.html)
- Workflow (http://www.siamhtml.com/git-workflow-in-a-team/)
