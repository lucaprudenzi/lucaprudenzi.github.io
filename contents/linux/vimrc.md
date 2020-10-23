---
layout: page
title: Vimrc
permalink: /linux/vimrc.html
---
```
" colorscheme
syntax on
set background=dark
" colorscheme murphy

" line for file name always visible
set laststatus=2

" keep cursor at the center while scrolling
set scrolloff=999

" new tab
nnoremap tt  :tabedit<Space>
nnoremap tl :tabnext<CR>
nnoremap th :tabprev<CR>
nnoremap tn :tabnew<CR>

" move between panes
nmap <silent> <A-Up> :wincmd k<CR>
nmap <silent> <A-Down> :wincmd j<CR>
nmap <silent> <A-Left> :wincmd h<CR>
nmap <silent> <A-Right> :wincmd l<CR>

" set mouse
set mouse=a

" disable arrow

noremap <Up> <Nop>
noremap <Down> <Nop>
noremap <Left> <Nop>
noremap <Right> <Nop>

" tab space
set tabstop=4 
set softtabstop=0 
set shiftwidth=4
set softtabstop=4
set smarttab
filetype plugin indent on
                
" number +relative = hybrid numbering
set number 

" move quickly up and down
noremap J 5j
vnoremap J 5j
noremap K 5k
vnoremap K 5k
" move to the first character in a line
noremap H ^
" move to the last character in a line
noremap L g_

" disable arrows
noremap  <Up> ""
noremap  <Down> ""
noremap  <Left> ""
noremap  <Right> ""

set nocompatible              " no vi comp
filetype off                  " required
nmap <C-n> :NERDTreeToggle<CR>

" airline config
" let g:airline#extensions#tabline#enabled = 1

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'preservim/nerdtree'
call vundle#end()            
filetype plugin indent on   
```
