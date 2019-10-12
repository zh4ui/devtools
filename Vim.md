# Vim

## Tips

* You can get latest gvim build from [vim-win32-installer](https://github.com/vim/vim-win32-installer/)

## Cheat Sheets

Graphical cheatsheet

* [Vim Cheat Sheat for Programmers by Michael Pohoreski](http://michael.peopleofhonoronly.com/vim/)
* [Vim Visual Cheat Sheet](https://hamwaves.com/vim.tutorial/en/index.html)

By function:

* [Vim cheatsheet](https://devhints.io/vim)
* [Vim Cheat Sheet](https://vim.rtorr.com/)
* [A Great Vim Cheat Sheet](http://vimsheet.com/)

List

* [5 Best VIM Cheat Sheet](https://rumorscity.com/2014/08/16/5-best-vim-cheat-sheet/)


### Show recent files

Vim keeps a list of recent files in `.viminfo`. Run `:oldfiles` to view the list. Run `:browse oldfiles` to select from the list by entering a number.

### option last set by who

E.g. Use `verbose set filetype` to show which script set `filetype` last time

### expand the name of the script

Instead of %, just use the special <sfile>; in a script (but not inside a function within a script!), it is expanded to the file name of the sourced script:

`:let s:local_path = expand('<sfile>:p:h')`

[source](https://stackoverflow.com/questions/13976270/get-path-of-current-file-being-sourced)

### change icon

> place your favorite icon in bitmaps/vim.ico in a directory of 'runtimepath'.  For example ~/vimfiles/bitmaps/vim.ico.

Online ico converters:

* https://icoconvert.com/
* https://convertico.com/

[How to change gVim icon on Windows?](https://vi.stackexchange.com/questions/16562/how-to-change-gvim-icon-on-windows)


### key-notation

`:h key-notaion`

### enable DirectX rendering for GViM

```
set renderoptions=type:directx,scrlines:1
```

[Vim の DirectX をさらに高速化した話](https://qiita.com/k-takata/items/9e16212acbc88564fd9f)


### 将Vim的<leader>映射到Space


By default your <leader> is \, backslash. You can check it with:

`:echo mapleader`

If this gives you an E121: Undefined variable: mapleader, it means it's set to the default of \. If it gives you something else, then it's that :-)

You can easily remap it. I mapped it to the space-bar:

`:let mapleader = "\<Space>"`

Note that the value of mapleader is used at the moment the mapping is defined. So this example:

`
let mapleader = ","
nnoremap <Leader>a :echo "Hey there ,"<CR>

let mapleader = "\<Space>"
nnoremap <Leader>a :echo "Hey there space"<CR>
`

Will produce two mappings: ,a and <Space>a.

This means that the current value of mapleader is not necessarily the value that was used to define your mappings!

In addition, there's the maplocalleader, which is the same as mapleader, except that it's used by <LocalLeader> and that it's local to the current buffer.

- [How can I find out what <Leader> is set to? And is it possible to remap <Leader>?](https://vi.stackexchange.com/questions/281/how-can-i-find-out-what-leader-is-set-to-and-is-it-possible-to-remap-leader)
- [Learn Vimscript the Hard Way: Leaders](http://learnvimscriptthehardway.stevelosh.com/chapters/06.html)
- [The "leader" mechanism](https://www.reddit.com/r/vim/wiki/the_leader_mechanism)
- [Mapping keys in Vim - Tutorial (Part 3)](https://vim.fandom.com/wiki/Mapping_keys_in_Vim_-_Tutorial_(Part_3))
- [Question about having space-bar as <leader>]https://www.reddit.com/r/vim/comments/2d2za5/question_about_having_spacebar_as_leader/)

