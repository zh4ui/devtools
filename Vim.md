# Vim

## Tips

* You can get latest gvim build from [vim-win32-installer](https://github.com/vim/vim-win32-installer/)

### Show recent files

Vim keeps a list of recent files in `.viminfo`. Run `:oldfiles` to view the list. Run `:browse oldfiles` to select from the list by entering a number.

### option last set by who

E.g. Use `verbose set filetype` to show which script set `filetype` last time

### expand the name of the script

Instead of %, just use the special <sfile>; in a script (but not inside a function within a script!), it is expanded to the file name of the sourced script:

`:let s:local_path = expand('<sfile>:p:h')`

[source](https://stackoverflow.com/questions/13976270/get-path-of-current-file-being-sourced)

## key-notation

`:h key-notaion`