# tmux-configuration
I followed this blog post [https://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/](https://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/).
I'm using MobaXterm and I still can't figure these out:
* The mouse wheel scroll
* Copying to system clipboard: on Mac, use iTerm2 as terminal and set iTerm2 > Preferences > “General” tab, and in the “Selection” section, check “Applications in terminal may access clipboard”.
* New window in current directory


## Use Ctrl+a as prefix key
```
# remap prefix from 'C-b' to 'C-a'
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix
```

## Use \ - for pane split
```
# split panes using | and -
bind \ split-window -h
bind - split-window -v
unbind '"'
unbind %
```

## Use Alt+arrow for pane switching
```
# switch panes using Alt-arrow without prefix
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D
```

## Mouse mode
```
# Enable mouse mode (tmux 2.1 and above)
set -g mouse on
```

## Position of statusbar
```
# Position of statusbar
set -g status-position bottom
set -g status-justify centre
```

## Start the number of windows and panes at 1, not 0
```
# Start windows and panes at 1, not 0
set -g base-index 1
setw -g pane-base-index 1
```

## Renumber the windows automatically
```
# Renumber the windows automatically after any window is closed 
set-option -g renumber-windows on
```

## Reload the config file
prefix :source-file /path/to/config/file

# Other Environment Setup on New Clusters

## Change the bash prompt

In ~/.bashrc file, add the following line at the end
```
PS1="\A \w> "
```
In the terminal, run the command:
```
source ~/.bashrc
```

## Change up arrow for bash history search 
Create a new ~/.inputrc file, add the following lines
```
## arrow up
"\e[A":history-search-backward
## arrow down
"\e[B":history-search-forward
```
In the terminal, run the command:
```
bind -f  ~/.inputrc
```

On Mac, create a new ~/.zshrc file, add the following lines
```
bindkey "^[[A" history-search-backward
bindkey "^[[B" history-search-forward
```
