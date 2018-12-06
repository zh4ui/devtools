# Shell

## zsh

**git pull in all sub directories**

```sh
for d in */; do pushd $d; echo $d; git pull; popd; done
```