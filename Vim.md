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