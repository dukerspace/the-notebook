### Sub Module
- git config --global alias.pullall '!f(){ git pull "$@" && git submodule update --init --recursive; }; f'

### Merge
- เริ่มต้นด้วยการ ไปที่ branch หลัก (master)
- จากนั้นก็สั่ง git merge branch_name จาก branch ที่ต้องการ มาที่ master
