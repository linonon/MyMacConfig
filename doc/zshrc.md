# Protobuf
export PROTOBUF=/usr/local/Cellar/protobuf

# Go env
export GOPATH=/Users/linonon/go 
export GOROOT=/usr/local/go
export GOPRIVATE="talent.com/server"

# PATH
export PATH=$PATH:$GOPATH/bin
export PATH=$PATH:/usr/local/Cellar/mysql@5.7/5.7.36/bin

# ZSH PATH
export ZSH="/Users/linonon/.oh-my-zsh"

# ZSH theme
ZSH_THEME="robbyrussell"

# Add wisely, as too many plugins slow down shell startup.
# std: $ZSH/plugins; custom: $ZSH_CUTSOM/plugins/
# plugins=(git)

source $ZSH/oh-my-zsh.sh

# System aliases
alias cl="clear && printf '\e[3J'"
alias cdw="cd ~/Workspace"
alias vimz="vim ~/.zshrc"
alias souz="source ~/.zshrc; cp -R ~/.zshrc /Users/linonon/Workspace/MyMacConfig/doc/zshrc.md"
alias pushMyMacConfig="cd ~/Workspace/MyMacConfig && git add . && git commit -m 'DOC: Update zshrc' && git push && cd -"

# DB aliases
alias start-mongo="mongod --port 27017 --dbpath /Users/linonon/Environment/data/db"
alias start-mysql="mysql.server start"
alias start-redis="redis-serve"

# Go aliases
alias gob="go build ."
alias gomi="go mod init"
alias gor="go run ."
alias gog="go get ."

# Game's cmd positions aliases
alias mydemo="cd ~/Workspace/game/slot_demo"
alias mymacconfig="cd /Users/linonon/Workspace/MyMacConfig"

alias breakaway="cd ~/Workspace/game/slot03/src"
alias candyparty="cd ~/Workspace/game/slot04/src"
alias firejoker="cd ~/Workspace/game/slot05/src"
alias slot03="breakaway"
alias slot04="candyparty"
alias slot05="firejoker"

alias lieng="cd /Users/linonon/Workspace/game/lieng/src"

### How to Use
### `cp -R ./zshrc.md ~/.zshrc`
