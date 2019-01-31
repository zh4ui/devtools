# Git

## Tips

### shallow git submodules

```sh
git submodule add --depth 1 -- repository path
git submodule update --depth -- [<path>...]
```

`--depth`  option is valid for add and update commands.
Create a 'shallow' clone with a history truncated to the specified number of revisions.


And git 2.10 Q3 2016 allows to record that with `git config -f .gitmodules submodule.<name>.shallow true`.

Ref: [How to make shallow git submodules?](https://stackoverflow.com/questions/2144406/how-to-make-shallow-git-submodules/17692710#17692710)


### list remote heads

if `git branch -r` doesn't work, try:

```sh
git ls-remote --heads <remote-name>
```


Source: [How do I list all remote branches in Git 1.7+?](https://stackoverflow.com/questions/3471827/how-do-i-list-all-remote-branches-in-git-1-7)

### delete a remote branch

`git push <repo_name> :<branch_name>`

### exclude files from git grep 

`git grep XXX -- './*' ':!*/test/*'`

[How to exclude certain directories/files from git grep search](https://stackoverflow.com/questions/10423143/how-to-exclude-certain-directories-files-from-git-grep-search)

If you use Git for Windows in cmd.exe, '"' should be used as the quote

`git grep xxx -- "./*" ":!*/test/*"`

You can put the above in a script named `git-grep1`, with the following content:

```sh
#!/usr/bin/bash

git grep -n "$@" -- './*' ':!*/test/*'
```

Put the script some where in PATH, so that git can find it. Therefore you can use `git grep1 xxx`.

> The script works even for Git for Windows.

## shallow submodule 

You can simply use: `git submodule add --depth 1 -- repository path`

For Git 2.9.0 and up, you can do this: `git clone --depth=1 --recursive --shallow-submodules repo_url`

[How to make shallow git submodules?](https://stackoverflow.com/questions/2144406/how-to-make-shallow-git-submodules)


### update all git repo in one directory

in shell, execute:

`for d in */; do pushd $d; echo $d; git pull; popd; done`

### clone without lfs

Two alternatives:

```sh
#1) Using the GIT_LFS_SKIP_SMUDGE variable:

GIT_LFS_SKIP_SMUDGE=1 git clone SERVER-REPOSITORY

# 2) Configuring the git-lfs smudge:

git config --global filter.lfs.smudge "git-lfs smudge --skip"
git clone SERVER-REPOSITORY

# To undo this configuration, execute:

git config --global filter.lfs.smudge "git-lfs smudge -- %f"
```

[How to clone/pull a git repository, ignoring LFS?](https://stackoverflow.com/questions/42019529/how-to-clone-pull-a-git-repository-ignoring-lfs)

## Git Client

* [tig](https://jonas.github.io/tig/). Text interface for Git repositories
