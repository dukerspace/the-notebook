### Sub Module
- git config --global alias.pullall '!f(){ git pull "$@" && git submodule update --init --recursive; }; f'
