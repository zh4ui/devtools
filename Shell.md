# Shell

## zsh

**git pull in all sub directories**

```sh
for d in */; do pushd $d; echo $d; git pull; popd; done
```

**(eval):1: _mv: function definition file not found**

```
rm -f ~/.zcompdump*
exec zsh -l
```


## clang

**find out default include path**

```
clang++ -Wp,-v -x c++ - -fsyntax-only < /dev/null
```

soruce: [Clang/GCC: find out default include path](http://fabic.net/notes/2018/01/22/Clang-find-out-default-include-path/)

## cmake

**How can I see the exact commands?**

```
cmake .
make VERBOSE=1
```

source: [Using CMake with GNU Make: How can I see the exact commands?](https://stackoverflow.com/questions/2670121/using-cmake-with-gnu-make-how-can-i-see-the-exact-commands)

## du

**calculate the size of each directory**

`du -h -s *`
