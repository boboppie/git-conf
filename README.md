Step 1
-----

Download git-completion.bash and git-prompt.sh from https://github.com/git/git/tree/master/contrib/completion

```
$ mv gitconfig ~/.gitconfig
$ mv git-completion.bash ~/.git-completion.bash
$ mv git-prompt.sh ~/.git-prompt.sh
$ source ~/.git-completion.bash
```

Step 2
-----
Add to $HOME/.bashrc

``` bash
# Prompt
red='\[\033[0;31m\]'
brown='\[\033[0;33m\]'
ubrown='\[\033[4;33m\]'
green='\[\033[0;32m\]'
lblue='\[\033[1;34m\]'
blue='\[\033[0;34m\]'
purp='\[\033[0;35m\]'
cyan='\[\033[0;36m\]'
nocol='\[\033[0m\]'

# workstation prompt
PSW="[$green\u$nocol@$brown\h$nocol:$purp\w$nocol]$cyan\!$nocol% "

# server prompt
PSS="[$lblue\$(date +%H:%M)$nocol][$green\u$nocol@$ubrown\h$nocol:$purp\w$nocol]$cyan\!$nocol% "

# standard prompt
if [ -f "$HOME/.git-prompt.sh" ]; then
  . "$HOME/.git-prompt.sh"
  PSW="[$green\u$nocol@$brown\h$nocol:$purp\w$nocol]$cyan\!$nocol$blue\$(__git_ps1)$nocol% "
  PSS="[$lblue\$(date +%H:%M)$nocol][$green\u$nocol@$brown\h$nocol:$purp\w$nocol]$cyan\!$nocol$blue\$(__git_ps1)$nocol% "
fi

export PS1=$PSW

if [ -f "$HOME/.git-completion.sh" ]; then
  . "$HOME/.git-completion.sh"
fi
```

then

```
$ source ~/.bashrc
```
