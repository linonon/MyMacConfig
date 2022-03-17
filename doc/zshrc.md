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
export PATH=$PATH:$BREW/bin
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
alias clpath="export PATH=$(perl -e 'print join(":", grep { not $seen{$_}++ } split(/:/, $ENV{PATH}))')"
alias vimz="vim ~/.zshrc"
alias souz="source ~/.zshrc"
alias vimv="vim ~/.vimrc"
alias c.="code ."
alias ce="code . && exit"
alias psag="ps aux | grep"
alias cm7="chmod 777"

### CD aliases
alias cdw="cd ~/Workspace"
alias cdg="cd ~/Workspace/game"
alias mmc="cd /Users/linonon/Workspace/MyMacConfig"
alias adcamp="cd ~/Workspace/GO-Advanced-training-camp"
alias cncamp="cd ~/Workspace/Cloud-native-gocamp"
alias lgg="cd ~/Workspace/Learn-Go-with-Github"
alias lcg="cd ~/Workspace/leetcode-go-TDD"
alias tss="cd ~/Workspace/technical-summary-sharing"

### Custom aliases
alias upload-zshrc="cp -R ~/.zshrc ~/Workspace/MyMacConfig/doc/zshrc.md"
alias upload-vimrc="cp -R ~/.vimrc ~/Workspace/MyMacConfig/doc/vimrc.md"
function pushc() {
	upload-zshrc
	upload-vimrc
	cd ~/Workspace/MyMacConfig 
	git pull && git add . 
	git commit -m 'DOC: Update Mac config' 
	git push 
	cd -
}

### DB aliases
alias start-mongo-notdeamon="mongod --port 27017 --dbpath /Users/linonon/Environment/data/db"
alias start-mongo="mongod --fork --port 27017 --dbpath /Users/linonon/Environment/data/db --logpath=/Users/linonon/Environment/data/db/log --logappend"
alias start-mysql="mysql.server start"
alias start-redis-notdeamon="redis-server"
alias start-redis="redis-server --daemonize yes"
function start-db() {
	start-mongo 
	start-redis 
	start-mysql
}
function stop-db() {
	redis-cli shutdown
	kill $(lsof -t -i:3306)
	mysql.server stop
}


### Go aliases
alias gob="go build ."
alias gomi="go mod init"
alias gomt="go mod tidy"
alias gor="go run ."
alias gog="go get ."
alias gov="go version"
alias gobrewv="echo $(cd /usr/local/Cellar/go; ls)"
function goch() {
	local go="/usr/local/bin/go"
	local gofmt="/usr/local/bin/gofmt"
	local goroot="/usr/local/go"

	if [[ $1 == 1.17 || $1 == 1.18 ]]; then
		sudo ln -fsn /usr/local/go$1/bin/go $go
		sudo ln -fsn /usr/local/go$1/bin/gofmt $gofmt
		sudo ln -fsn /usr/local/go$1 $goroot
	elif [[ $1 == "brew" ]]; then
		sudo ln -fsn /usr/local/Cellar/go/$(gobrewv)/bin/go $go
		sudo ln -fsn /usr/local/Cellar/go/$(gobrewv)/bin/gofmt $gofmt
		sudo ln -fsn /usr/local/Cellar/go/$(gobrewv) $goroot
	else
		echo "go@$1 is not installed"
	fi
}

### Docker aliases
alias d="docker"
alias dps="docker ps"
alias datt="docker attach"
alias dr="docker run"
alias di="docker images"
alias dcon="docker container"

### Python aliases
alias py="python3"
alias pi="pip3"

### How to Use
### `cp -R ./zshrc.md ~/.zshrc`

### gcloud alias
alias gjp="gcloud compute ssh --zone "asia-northeast1-b" "instance-2"  --project "conductive-set-341607""

### The next line updates PATH for the Google Cloud SDK.
if [ -f '/Users/linonon/Workspace/google-cloud-sdk/path.zsh.inc' ]; then . '/Users/linonon/Workspace/google-cloud-sdk/path.zsh.inc'; fi

### The next line enables shell command completion for gcloud.
if [ -f '/Users/linonon/Workspace/google-cloud-sdk/completion.zsh.inc' ]; then . '/Users/linonon/Workspace/google-cloud-sdk/completion.zsh.inc'; fi
