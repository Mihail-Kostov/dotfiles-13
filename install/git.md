# Git

```
brew install git
brew link --overwrite git
brew info git
```

And update your `~/.bash_prompt` to add autocomplete and prompt:

```
#!/bin/bash

#############################################################################
# Change Terminal tab name to dir basename
#############################################################################

PROMPT_COMMAND='echo -n -e "\033]0;${PWD##*/}\007"'

#############################################################################
# Bash autocomplet
#############################################################################

if [ -f $(brew --prefix)/etc/bash_completion ]; then
   . $(brew --prefix)/etc/bash_completion
fi

#############################################################################
# GIT prompt
#############################################################################

GIT_PS1_SHOWDIRTYSTATE=true
GIT_PS1_SHOWUNTRACKEDFILES=
GIT_PS1_SHOWCOLORHINTS=true
GIT_PS1_SHOWUPSTREAM="auto"
GIT_PS1_DESCRIBE_STYLE="contains"

#############################################################################
# Bash prompt
#############################################################################

# \d – Current date
# \t – Current time
# \h – Host name
# \# – Command number
# \u – User name
# \W – Current working directory (ie: Desktop/)
# \w – Current working directory, full path (ie: /Users/Admin/Desktop)
# export PS1="\u@\h\w: "

export PS1='\w: $(__git_ps1 "\[\033[01;31m\]%s \[\033[00m\]")'
```

## Git Extras

Install [git extras](https://github.com/tj/git-extras):

```
brew install git-extras
```