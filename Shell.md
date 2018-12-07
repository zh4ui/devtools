# Shell

## zsh

**git pull in all sub directories**

```sh
for d in */; do pushd $d; echo $d; git pull; popd; done
```

## clang

**find out default include path**

```
clang++ -Wp,-v -x c++ - -fsyntax-only < /dev/null
```

soruce: [Clang/GCC: find out default include path](http://fabic.net/notes/2018/01/22/Clang-find-out-default-include-path/)