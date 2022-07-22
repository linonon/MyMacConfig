export USER_NAME=oliver
export SSH_KEY=~/.ssh/id_rsa
export TELEGRAM_TOKEN="5130690963:AAGNv_DU-_aFB_FoCqlksrn5WhyElxB6WOk"


### Export
export PROTOBUF=/usr/local/Cellar/protobuf
export PYTHON3=$HOME/Library/Python/3.8

export GOPATH=$HOME/go
export GOROOT=/usr/local/go
export GOPRIVATE="talent.com/server"
export CARGOPATH="$HOME/.cargo/bin"

export BREW=/usr/local

export TK="/usr/local/opt/tcl-tk/bin"
export LDFLAGS="-L/usr/local/opt/tcl-tk/lib"
export CPPFLAGS="-I/usr/local/opt/tcl-tk/include"
export PKG_CONFIG_PATH="/usr/local/opt/tcl-tk/lib/pkgconfig"

### PATH
export PATH=$TK:$PATH
export PATH=$BREW/bin:$PATH
export PATH=$GOPATH/bin:$PATH
export PATH=$CARGOPATH/bin:$PATH
export PATH=$PYTHON3/bin:$PATH


### ZSH PATH
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="agnoster"
# ZSH_THEME="arrow"
# ZSH_THEME="jonathan"

### Add wisely, as too many plugins slow down shell startup.
### std: $ZSH/plugins; custom: $ZSH_CUTSOM/plugins/
### plugins=(git)
plugins=(
	cdgame
	z
	zsh-syntax-highlighting
	zsh-autosuggestions
)

source $ZSH/oh-my-zsh.sh

### System aliases
alias cl="clear && printf '\e[3J'"
alias clpath="export PATH=$(perl -e 'print join(":", grep { not $seen{$_}++ } split(/:/, $ENV{PATH}))')"
# alias vim="nvim"
alias vimz="vim ~/.zshrc"
# alias nvimz="nvim ~/.zshrc"
alias souz="source ~/.zshrc"
alias vimv="vim ~/.vimrc"
alias c.="code ."
alias ce="code . && exit"
alias psag="ps aux | grep"
alias cm7="chmod 777"
alias sls="screen -ls"
alias sr="screen -r"
alias llg="ll | grep"
alias autocommit="sh ~/Workspace/go-combat/timed-task/sh/autocommit.sh"
alias pwdd="pwd && pwd | clipcopy"

### CD aliases
alias cdw="cd ~/Workspace"
alias cdd="cd ~/Downloads"
alias cdg="cd ~/Workspace/game"
alias mmc="cd ~/Workspace/MyMacConfig"
alias adcamp="cd ~/Workspace/GO-Advanced-training-camp"
alias cncamp="cd ~/Workspace/Cloud-native-gocamp"
alias lgg="cd ~/Workspace/Learn-Go-with-Github"
alias lcg="cd ~/Workspace/leetcode-go-TDD"
alias tss="cd ~/Workspace/technical-summary-sharing"
alias lp="cd ~/Workspace/learning-process"
alias gc="cd ~/Workspace/go-combat"
alias rl="cd ~/Workspace/Rust-learning"
alias rbp="cd ~/Workspace/rust-by-practice"

### Custom aliases
alias upload-zshrc="cp -R ~/.zshrc ~/Workspace/MyMacConfig/doc/zshrc.md"
alias upload-vimrc="cp -R ~/.vimrc ~/Workspace/MyMacConfig/doc/vimrc.md"
function pushc() {
	upload-zshrc
	upload-vimrc
	mmc
	gitpacp 'DOC: Update Mac config'
	cd -
}
function gitpacp() {
	git pull && git add .
	if [[ $1 != "" ]]; then
		git commit -m $1
	else 
		git commit -m "Push without message"
	fi	
	git push
}

### Nginx aliases
alias ng="nginx"
alias ngs="nginx -s stop"
alias ngr="nginx -s reload"
alias ngt="nginx -t"

### DB aliases
alias start-redis-no-daemon="redis-server"
alias start-mongo-no-daemon="mongod --port 27017 --dbpath $HOME/Environment/data/db"
alias start-mongo-daemon="mongod --fork --port 27017 --dbpath $HOME/Environment/data/db --logpath=$HOME/Environment/data/db/log --logappend"
alias start-redis-daemon="redis-server --daemonize yes"
alias start-mysql="mysql.server start"

alias stop-redis="redis-cli shutdown"
alias stop-mongo="kill $(lsof -t -i:27017)"
alias stop-mysql="mysql.server stop"	

alias start-db="start-mongo-daemon ; start-redis-daemon ; start-mysql"
alias stop-db="stop-redis ; stop-mongo ; stop-mysql"

### Rust aliases
alias rr="cargo run"
alias rb="cargo build"
alias rc="cargo clippy"
alias rn="cargo new"

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

	if [[ $1 == 1.17 || $1 == 1.18 ]]; then
		sudo ln -fsn /usr/local/go$1/bin/go $go
		sudo ln -fsn /usr/local/go$1/bin/gofmt $gofmt
		sudo ln -fsn /usr/local/go$1 $GOROOT
	elif [[ $1 == "brew" ]]; then
		sudo ln -fsn /usr/local/Cellar/go/$(gobrewv)/libexec/bin/go $go
		sudo ln -fsn /usr/local/Cellar/go/$(gobrewv)/libexec/bin/gofmt $gofmt
		sudo ln -fsn /usr/local/Cellar/go/$(gobrewv)/libexec $GOROOT
	else
		echo "go version: '$1' not found"
	fi

	gov
}

### Go Tools aliases
alias fishtrack="$HOME/Workspace/fishing-track-analyze/fish-analyze"
alias fishtracklocal="$HOME/Workspace/fishing-track-analyze/fish-analyze-local"

### Docker aliases
alias d="docker"
alias dps="docker ps"
alias dr="docker run"
alias dim="docker images"
alias dcon="docker container"
function dex() {
	if [[ $2 != "" ]]; then
		docker exec -it $1 $2
	else
		docker exec -it $1 zsh
	fi
}

### Python aliases
alias py="/usr/bin/python3"
alias pip="/usr/bin/pip3"

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

### New line for input (ZSH_THEME: agnoster)
function prompt_context(){}
function prompt_end() {
  if [[ -n $CURRENT_BG ]]; then
      print -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR"
  else
      print -n "%{%k%}"
  fi

  print -n "%{%f%}"
  CURRENT_BG=''

  #Adds the new line and ➜ as the start character.
  printf "\n(cmd)";
}

