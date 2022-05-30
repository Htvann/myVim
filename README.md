"Invalid arguments for function plug#
" Bật highlight cú pháp cho một loại file (như .py, .cpp, .xml) syntax enable
syntax on
filetype plugin indent on
colorscheme onedark 
set bg=dark
" Hiện số thứ tự của dòng
set number


" Hiện số thứ tự theo cách hybrid
" Dòng hiện tại đánh số là số dòng thực tế, 
" dòng trên và dòng dưới là 1, và cứ thế đối với các dòng khác
set number relativenumber

" Chỉnh 4 space mỗi tab
set tabstop=4

" Chỉnh 4 space mỗi indent
set shiftwidth=4

" Sử dụng space character thay tab character khi nhấn Tab
set expandtab

" Tự động indent khi xuống hàng
set autoindent

" Sử dụng clipboard hệ thống thay buffer của vim
set clipboard=unnamedplus

" Chỉnh độ delay (ms) giữa lần chuyển chế độ
set ttimeoutlen=50

" Cau hinh Vim airline
let g:airline_theme='bubblegum'
let g:airline_powerline_fonts=1

" Cau hinh symbol hien thi dung
if !exists('g:airline_symbols')
  let g:airline_symbols = {}
endif
  
"" powerline symbols
let g:airline_left_sep = ''
let g:airline_left_alt_sep = ''
let g:airline_right_sep = ''
let g:airline_right_alt_sep = ''
let g:airline_symbols.branch = ''
let g:airline_symbols.readonly = ''
let g:airline_symbols.linenr = 'ln'
let g:airline_symbols.maxlinenr = ''
let g:airline_symbols.dirty='⚡'
let g:airline_symbols.colnr='col'"

"Cau hinh hien thi brandname
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#hunks#enabled=0
let g:airline#extensions#hunks#coc_git = 1

"Cau hinh nerdTree
nnoremap <leader>n :NERDTreeFocus<CR>
nnoremap <C-n> :NERDTree<CR>
nnoremap <C-t> :NERDTreeToggle<CR>
nnoremap <C-f> :NERDTreeFind<CR>

"Cau hinh js
set nocompatible

"cau hinh iconfile
set encoding=UTF-8


" Gọi đầu tiên
call plug#begin('~/.vim/plugged')
" cai dat giao dien vim
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'jiangmiao/auto-pairs'
Plug 'preservim/nerdtree'
Plug 'preservim/nerdcommenter'
Plug 'ryanoasis/vim-devicons'
Plug 'tpope/vim-surround'
Plug 'wakatime/vim-wakatime'
Plug 'mattn/emmet-vim'
" cai dat react, js, htmlcss...
Plug 'sheerun/vim-polyglot'
Plug 'neoclide/coc.nvim', {'branch': 'release'}
" post install (yarn install | npm install) then load plugin only for editing supported files
Plug 'prettier/vim-prettier', {
  \ 'do': 'yarn install --frozen-lockfile --production',
  \ 'for': ['javascript', 'typescript', 'css', 'less', 'scss', 'json', 'graphql', 'markdown', 'vue', 'svelte', 'yaml', 'html'] }
" Kết thúc việc cài plugin
call plug#end()
