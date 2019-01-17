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

## shallow submodule 

You can simply use: `git submodule add --depth 1 -- repository path`

For Git 2.9.0 and up, you can do this: `git clone --depth=1 --recursive --shallow-submodules repo_url`

[How to make shallow git submodules?](https://stackoverflow.com/questions/2144406/how-to-make-shallow-git-submodules)


## Git Client

* [tig](https://jonas.github.io/tig/). Text interface for Git repositories
