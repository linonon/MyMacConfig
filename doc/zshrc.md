### Protobuf
export PROTOBUF=/usr/local/Cellar/protobuf

### Go env
export GOPATH=/Users/linonon/go 
export GOROOT=/usr/local/go
export GOPRIVATE="talent.com/server"

### Brew
export BREW=/usr/local

### MYSQL
export MYSQL=/usr/local/Cellar/mysql@5.7/5.7.37/bin

### PATH
export PATH=$PATH:$GOROOT/bin:$BREW/bin
export PATH=$PATH:$GOPATH/bin
export PATH=$PATH:$MYSQL

### ZSH PATH
export ZSH="/Users/linonon/.oh-my-zsh"

### ZSH theme
ZSH_THEME="robbyrussell"

### Add wisely, as too many plugins slow down shell startup.
### std: $ZSH/plugins; custom: $ZSH_CUTSOM/plugins/
### plugins=(git)
plugins=(cdgame)

source $ZSH/oh-my-zsh.sh

### System aliases
alias cl="clear && printf '\e[3J'"
alias vimz="vim ~/.zshrc"
alias souz="source ~/.zshrc"
alias vimv="vim ~/.vimrc"
alias c.="code ."
alias ce="code . && exit"
alias psag="ps aux | grep"

### CD aliases
alias cdw="cd ~/Workspace"
alias mmc="cd /Users/linonon/Workspace/MyMacConfig"
alias adcamp="cd ~/Workspace/GO-Advanced-training-camp"
alias lgg="cd ~/Workspace/Learn-Go-with-Github"
alias lcg="cd ~/Workspace/leetcode-go-TDD"
alias tss="cd ~/Workspace/technical-summary-sharing"

### Custom aliases
alias upload-zshrc="cp -R ~/.zshrc ~/Workspace/MyMacConfig/doc/zshrc.md"
alias upload-vimrc="cp -R ~/.vimrc ~/Workspace/MyMacConfig/doc/vimrc.md"
alias upload-vscodetheme="cp -R ~/.vscode/extensions/github.github-vscode-theme-6.0.0/themes/dark-default.json ~/Workspace/MyMacConfig/vscode/github-theme/dark-default.json"
alias pushc="upload-zshrc && upload-vimrc && upload-vscodetheme && cd ~/Workspace/MyMacConfig && git pull && git add . && git commit -m 'DOC: Update Mac config' && git push && cd -"

alias download-vscodetheme="cp -R ~/Workspace/MyMacConfig/vscode/github-theme/dark-default.json ~/.vscode/extensions/github.github-vscode-theme-6.0.0/themes/dark-default.json"

### DB aliases
alias start-mongo-notbackground="mongod --port 27017 --dbpath /Users/linonon/Environment/data/db"
alias start-mongo="mongod --fork --port 27017 --dbpath /Users/linonon/Environment/data/db --logpath=/Users/linonon/Environment/data/db/log --logappend"
alias start-mysql="mysql.server start"
alias start-redis-notbackground="redis-server"
alias start-redis="redis-server --daemonize yes"

### Go aliases
alias gob="go build ."
alias gomi="go mod init"
alias gor="go run ."
alias gog="go get ."
alias gov="go version"

### How to Use
### `cp -R ./zshrc.md ~/.zshrc`
