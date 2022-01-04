### Protobuf
export PROTOBUF=/usr/local/Cellar/protobuf

### Go env
export GOPATH=/Users/linonon/go 
export GOROOT=/usr/local/go
export GOPRIVATE="talent.com/server"

### PATH
export PATH=$PATH:$GOPATH/bin
export PATH=$PATH:/usr/local/Cellar/mysql@5.7/5.7.36/bin

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
alias cdw="cd ~/Workspace"
alias vimz="vim ~/.zshrc"
alias souz="source ~/.zshrc"
alias vimv="vim ~/.vimrc"

### Custom aliases
alias mymacconfig="cd /Users/linonon/Workspace/MyMacConfig"
alias updatez="cp -R ~/.zshrc ~/Workspace/MyMacConfig/doc/zshrc.md"

alias updatev="cp -R ~/.vimrc ~/Workspace/MyMacConfig/doc/vimrc.md"

alias pushc="updatez && updatev && cd ~/Workspace/MyMacConfig && git add . && git commit -m 'DOC: Update Mac config' && git push && cd -"

### DB aliases
alias start-mongo="mongod --port 27017 --dbpath /Users/linonon/Environment/data/db"
alias start-mysql="mysql.server start"
alias start-redis="redis-server"

### Go aliases
alias gob="go build ."
alias gomi="go mod init"
alias gor="go run ."
alias gog="go get ."

### How to Use
### `cp -R ./zshrc.md ~/.zshrc`
