---
layout: page
title: Tmux conf
permalink: /linux/tmux.html
---

# unbind default prefix and set it to ctrl-a
unbind C-b
set -g prefix M-a
bind M-a send-prefix

# make delay shorter
set -sg escape-time 0


#### key bindings ####

# reload config file
bind r source-file ~/.tmux.conf \; display ".tmux.conf reloaded!"

# quickly open a new window
bind N new-window

# synchronize all panes in a window
# bind-key y setw synchronize-panes

# pane movement shortcuts (same as vim)
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R

# enable mouse support for switching panes/windows
set -g mouse off


#### copy mode : vim ####
# set vi mode for copy mode
setw -g mode-keys vi

bind-key -T copy-mode-vi v send-keys -X begin-selection
#bind-key -T copy-mode-vi y send-keys -X copy-selection
bind -T copy-mode-vi r send-keys -X rectangle-toggle
bind -T copy-mode-vi y send-keys -X copy-pipe-and-cancel 'xclip -in -selection clipboard'
bind-key p run "xclip -o -sel clip | tmux load-buffer - ; tmux paste-buffer"


# disable whitespace indicator inside vim
# autocmd VimEnter * AirlineToggleWhitespace

# open new pane in the same directory
bind '"' split-window -c "#{pane_current_path}"
bind % split-window -h -c "#{pane_current_path}"
bind c new-window -c "#{pane_current_path}"

# copy mode using 'Esc'
unbind-key [
bind Escape copy-mode
unbind-key P
# start selection with 'space' and copy using 'y'
#bind-key -t vi-copy 'y' copy-selection

# paste using 'p'
#unbind p
#bind p paste-buffer

# keep vim colorscheme
set -g default-terminal 'screen-256color'

# Set scrollback buffer to 10000
set -g history-limit 10000

# let g:airline#extensions#tabline#enabled = 0
# list of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-resurrect'
set -g @plugin 'tmux-plugins/tmux-continuum'
set -g @continuum-restore 'on'
set -g @plugin 'jimeh/tmux-themepack'
set -g @themepack 'powerline/block/blue'
# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run -b '~/.tmux/plugins/tpm/tpm'
