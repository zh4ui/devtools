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