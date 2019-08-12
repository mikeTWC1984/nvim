```
call plug#begin('~/.vim/plugged')

Plug 'neoclide/coc.nvim', {'branch': 'release'}
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'tpope/vim-fugitive'
Plug 'scrooloose/nerdtree'
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'vim-airline/vim-airline'
"Plug 'OmniSharp/omnisharp-vim'
Plug 'tpope/vim-dispatch'
Plug 'Shougo/vimproc.vim', {'do' : 'make'}
Plug 'w0rp/ale'
Plug 'lifepillar/vim-solarized8'
Plug 'challenger-deep-theme/vim', { 'as': 'challenger-deep' }
Plug 'NLKNguyen/papercolor-theme'
Plug 'sheerun/vim-polyglot'
Plug 'ryanoasis/vim-devicons'

call plug#end()

set clipboard=unnamedplus
vnoremap <C-X> "+x
vnoremap <S-Del> "+x
vnoremap <C-C> "+y
vnoremap <C-Insert> "+y
map <C-V>       "+gP
map <C-A> ggVG <CR>
cmap <C-V>      <C-R>+
cmap <S-Insert>     <C-R>+


set encoding=utf8
filetype plugin indent  on

"autocmd FileType ps1 setlocal shell=pwsh

set autoindent
set expandtab
set shiftwidth=2
set mouse=a 
set relativenumber
set background=dark
colorscheme PaperColor
"noremap <silent> <space> :exe "normal i".nr2char(getchar())<CR>

" tab navigation
map <S-Right> :tabn<CR>
map <S-Left>  :tabp<CR>
map <F2> :NERDTreeToggle<CR>
"autocmd BufWritePost * NERDTreeFocus | execute 'normal R' | wincmd p

map <F29>  :w <bar> let c="term pwsh -NoExit -f " . expand('%:p') <bar> execute c <CR>
map <F8> :CocCommand powershell.evaluateSelection <CR>
map <F5> :CocCommand powershell.execute <CR>
inoremap <C-j> :CocList snippets <CR>
map <C-j> <Plug>(coc-snippets-expand)

nnoremap<C-x> :q!<CR>
map<F12> :qa!<CR>
set splitbelow

set laststatus=2


" split/vsplit resize
map <C-Right> <C-w><<CR>
map <C-Left> <C-w>><CR>
map <C-Up> <C-w>-<CR>
map <C-Down> <C-w>+<CR>

" airline settings
"let g:airline_powerline_fonts = 1
set t_Co=256

"Airline : install powerline fonts first (sudo apt-get install fonts-powerline)

"set guifont=Liberation\ Mono\ for\ Powerline\ 11
set guifont=DejaVu\ Sans\ Mono\ Nerd\ Font\ 14
"set guifont=DroidSansMono\ Nerd\ Font:h12

" TAB COMPLETION
inoremap <expr> <Tab> pumvisible() ? "\<C-n>" : "\<Tab>"
inoremap <expr> <S-Tab> pumvisible() ? "\<C-p>" : "\<S-Tab>"
inoremap <expr> <cr> pumvisible() ? "\<C-y>" : "\<C-g>u\<CR>"


let g:WebDevIconsUnicodeDecorateFolderNodes = 1
let g:DevIconsEnableFoldersOpenClose = 1
let g:DevIconsDefaultFolderOpenSymbol='' " symbol for open folder (f07c)
let g:WebDevIconsUnicodeDecorateFolderNodesDefaultSymbol='' " symbol for closed folder (f07b)


let g:airline_theme='angr'
let g:airline_solarized_bg='dark'
let g:airline_powerline_fonts=1
let g:airline_inactive_collapse=1
let g:airline_inactive_alt_sep=0
let g:airline_detect_modified=1
let g:airline#extensions#wordcount#enabled = 1
let g:airline#extensions#fugitiveline#enabled = 1
let g:airline#extensions#branch#enabled = 1
let g:airline_detect_spell=1
let g:airline_detect_spelllang=1
let g:airline_exclude_preview = 1
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#buffer_nr_show = 1
let g:airline#extensions#tabline#buffer_nr_format = '%s: '
let g:airline#extensions#tabline#fnamemod = ':t'
set ttimeoutlen=50

"let g:OmniSharp_server_stdio = 1
"let g:OmniSharp_server_use_mono = 1
"let g:OmniSharp_server_path = '~/.omnisharp/omnisharp-roslyn/run'
"let g:OmniSharp_server_use_mono = 1


" Timeout in seconds to wait for a response from the server
"let g:OmniSharp_timeout = 5

" Don't autoselect first omnicomplete option, show options even if there is only
" one (so the preview documentation is accessible). Remove 'preview' if you
" don't want to see any documentation whatsoever.
"set completeopt=longest,menuone,preview

" Fetch full documentation during omnicomplete requests.
" By default, only Type/Method signatures are fetched. Full documentation can
" still be fetched when you need it with the :OmniSharpDocumentation command.
"let g:omnicomplete_fetch_full_documentation = 1

```
