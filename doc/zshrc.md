### Protobuf
export PROTOBUF=/usr/local/Cellar/protobuf

### Go env
export GOPATH=/Users/linonon/go
export GOROOT=/usr/local/go
export GOPRIVATE="talent.com/server"

### Brew
export BREW=/usr/local

### PATH
export PATH=$BREW/bin:$PATH
export PATH=$GOPATH/bin:$PATH


### ZSH PATH
export ZSH="/Users/linonon/.oh-my-zsh"

### ZSH theme
ZSH_THEME="robbyrussell"

### Add wisely, as too many plugins slow down shell startup.
### std: $ZSH/plugins; custom: $ZSH_CUTSOM/plugins/
### plugins=(git)
plugins=(
	cdgame
)

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
alias sls="screen -ls"
alias sr="screen -r"
alias llg="ll | grep"

### CD aliases
alias cdw="cd ~/Workspace"
alias cdg="cd ~/Workspace/game"
alias mmc="cd ~/Workspace/MyMacConfig"
alias adcamp="cd ~/Workspace/GO-Advanced-training-camp"
alias cncamp="cd ~/Workspace/Cloud-native-gocamp"
alias lgg="cd ~/Workspace/Learn-Go-with-Github"
alias lcg="cd ~/Workspace/leetcode-go-TDD"
alias tss="cd ~/Workspace/technical-summary-sharing"
alias lp="cd ~/Workspace/learning-process"
alias gc="cd ~/Workspace/go-combat"

### Custom aliases
alias upload-zshrc="cp -R ~/.zshrc ~/Workspace/MyMacConfig/doc/zshrc.md"
alias upload-vimrc="cp -R ~/.vimrc ~/Workspace/MyMacConfig/doc/vimrc.md"
function pushc() {
	upload-zshrc
	upload-vimrc
	mmc
	gpacp 'DOC: Update Mac config'
	cd -
}
function gpacp() {
	git pull && git add .
	if [[ $1 != "" ]]; then
		git commit -m $1
	else 
		git commit -m "Push without message"
	fi	
	git push
}

### DB aliases
alias start-redis-no-daemon="redis-server"
alias start-mongo-no-daemon="mongod --port 27017 --dbpath /Users/linonon/Environment/data/db"
alias start-mongo-daemon="mongod --fork --port 27017 --dbpath /Users/linonon/Environment/data/db --logpath=/Users/linonon/Environment/data/db/log --logappend"
alias start-redis-daemon="redis-server --daemonize yes"
alias start-mysql="mysql.server start"

alias stop-redis="redis-cli shutdown"
alias stop-mongo="kill $(lsof -t -i:3306)"
alias stop mysql="mysql.server stop"	

alias start-db="start-mongo-daemon && start-redis-daemon && start-mysql"
alias stop-db="stop-redis && stop-mongo && stop-mysql"

export PATH="/usr/local/opt/tcl-tk/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/tcl-tk/lib"
export CPPFLAGS="-I/usr/local/opt/tcl-tk/include"
export PKG_CONFIG_PATH="/usr/local/opt/tcl-tk/lib/pkgconfig"

### How to Use
### `cp -R ./zshrc.md ~/.zshrc`

### gcloud alias
alias gjp="gcloud compute ssh --zone "asia-northeast1-b" "instance-2"  --project "conductive-set-341607""

### The next line updates PATH for the Google Cloud SDK.
if [ -f '/Users/linonon/Workspace/google-cloud-sdk/path.zsh.inc' ]; then . '/Users/linonon/Workspace/google-cloud-sdk/path.zsh.inc'; fi

### The next line enables shell command completion for gcloud.
if [ -f '/Users/linonon/Workspace/google-cloud-sdk/completion.zsh.inc' ]; then . '/Users/linonon/Workspace/google-cloud-sdk/completion.zsh.inc'; fi
