# tmux-configuration
I mostly followed this blog post[https://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/](https://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/).


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

## Renumber the windows automatically
```
# Renumber the windows automatically after any window is closed 
set-option -g renumber-windows on
```

