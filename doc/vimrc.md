syntax on
set mouse=a
set clipboard=unnamed
set tabstop=4 softtabstop=4 shiftwidth=4 

set nu
hi LineNr cterm=bold ctermfg=DarkGrey ctermbg=NONE

set cursorline
hi CursorLineNr cterm=bold ctermfg=Green ctermbg=NONE

call plug#begin('~/.vim/plug')
Plug 'morhetz/gruvbox'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'justinmk/vim-sneak'
Plug 'tpope/vim-surround'
call plug#end()
