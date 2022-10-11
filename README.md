## Installation
```
apt install zsh
```

## Standardshell 
```
chsh -s /usr/bin/zsh lorenz
```

## open new shell; in menu on new shell choose recommended configuration for .zshenv, .zprofile, .zshrc, .zlogin
```
Wizard options: nerdfont-complete + powerline, small icons, classic, unicode, lightest, angled separators, sharp heads, flat tails, 2 lines, dotted, no frame, compact, many icons, concise, transient_prompt, instant_prompt=verbose.
```

## install oh-my-zsh
```
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```

## install front (for powerlevel10k theme)
download and install (for WSL in Windows-System )
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf

## choose front in WSL for Shell

## install theme
https://github.com/romkatv/powerlevel10k#installation

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```


## Following Steps in  in ~/.zshrc

### ~/.zshrc: choose theme
```
ZSH_THEME='powerlevel10k/powerlevel10k'
```

### ~/.zshrc: "zsh-autosuggestions" install plugin
https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh

### ~/.zshrc: "zsh-syntax-highlighting" install plugin
https://github.com/zsh-users/zsh-syntax-highlighting

## default und installierte Plugins aktivieren
change line to:
```
plugins=(git kubectl ssh-agent helm terraform zsh-autosuggestions zsh-syntax-highlighting colored-man-pages)
```

### ~/.zshrc: config ssh-agent
zstyle :omz:plugins:ssh-agent agent-forwarding yes
zstyle :omz:plugins:ssh-agent lazy yes
zstyle :omz:plugins:ssh-agent lifetime 1h

### ~/.zshrc: add az autocompletion
(muss unter nash bereits funktionieren)
```
source /etc/bash_completion.d/azure-cli
```

### load new settings
exec zsh

## Following Steps in  in ~/.p10k.zsh

### ~/.p10k.zsh: kubectl context immer zeigen
change line
``` 
POWERLEVEL9K_KUBECONTEXT_DEFAULT_CONTENT_EXPANSION+='${P9K_KUBECONTEXT_CLOUD_CLUSTER:-${P9K_KUBECONTEXT_NAME}}'
```
to
```
POWERLEVEL9K_KUBECONTEXT_DEFAULT_CONTENT_EXPANSION+='${P9K_KUBECONTEXT_CLUSTER:-${P9K_KUBECONTEXT_NAME}}'
```

### ~/.p10k.zsh: Pfad kürzen für schmales Fenster
Pfad auf 60 prozent statt auf 80 kürzen:
```
typeset -g POWERLEVEL9K_DIR_MAX_LENGTH=60
```

### ~/.p10k.zsh: Tansient for new directory
```
typeset -g POWERLEVEL9K_TRANSIENT_PROMPT=same-dir
```

### Transient for Git-Branch (noch nie getetstet)
https://github.com/romkatv/powerlevel10k/issues/1603

### load new settings
exec zsh

# Kubecolor (Noch nicht erfolgreich getetstet)
https://github.com/hidetatz/kubecolor 


# install Krew
https://krew.sigs.k8s.io/docs/user-guide/setup/install/




