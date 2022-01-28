### Protobuf
export PROTOBUF=/usr/local/Cellar/protobuf

### Go env
export GOPATH=/Users/linonon/go 
export GOROOT=/usr/local/go
export GOPRIVATE="talent.com/server"

### Brew
export BREW=/usr/local

### PATH
export PATH=$PATH:$GOROOT/bin:$BREW/bin:
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
alias vimz="vim ~/.zshrc"
alias souz="source ~/.zshrc"
alias vimv="vim ~/.vimrc"
alias c.="code ."
alias ce="code . && exit"

### CD aliases
alias cdw="cd ~/Workspace"
alias mmc="cd /Users/linonon/Workspace/MyMacConfig"
alias adcamp="cd ~/Workspace/GO-Advanced-training-camp"
alias lgg="cd ~/Workspace/Learn-Go-with-Github"
alias lcg="cd ~/Workspace/leetcode-go-TDD"
alias tss="cd ~/Workspace/technical-summary-sharing"

### Custom aliases
alias updatez="cp -R ~/.zshrc ~/Workspace/MyMacConfig/doc/zshrc.md"
alias updatev="cp -R ~/.vimrc ~/Workspace/MyMacConfig/doc/vimrc.md"
alias pushc="updatez && updatev && cd ~/Workspace/MyMacConfig && git pull && git add . && git commit -m 'DOC: Update Mac config' && git push && cd -"

### DB aliases
alias start-mongo="mongod --port 27017 --dbpath /Users/linonon/Environment/data/db"
alias start-mysql="mysql.server start"
alias start-redis="redis-server"

### Go aliases
alias gob="go build ."
alias gomi="go mod init"
alias gor="go run ."
alias gog="go get ."
alias gov="go version"

### How to Use
### `cp -R ./zshrc.md ~/.zshrc`
