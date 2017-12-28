## Git
#### Try https://try.github.io/
#### เริ่มต้น
- git init
- git remote add origin http://github.com/??
- git add --all
- git commit -m "Init"
- git push origin

#### Sub Module
- git config --global alias.pullall '!f(){ git pull "$@" && git submodule update --init --recursive; }; f'

#### Merge
- เริ่มต้นด้วยการ ไปที่ branch หลัก (master)
- จากนั้นก็สั่ง git merge branch_name จาก branch ที่ต้องการ มาที่ master

## Gitlab
#### git diff 
![diff](/files/gitlabdiff.jpg "gitlab diff")