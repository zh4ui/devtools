# Git

## Tips

### shallow git submodules

```sh
git submodule add --depth 1 -- repository path
git submodule update --depth -- [<path>...]
```

`--depth`  option is valid for add and update commands.
Create a 'shallow' clone with a history truncated to the specified number of revisions.

For Git 2.9.0 and up, you can do this: `git clone --depth=1 --recursive --shallow-submodules repo_url`

And git 2.10 Q3 2016 allows to record that with `git config -f .gitmodules submodule.<name>.shallow true`.

Ref: [How to make shallow git submodules?](https://stackoverflow.com/questions/2144406/how-to-make-shallow-git-submodules/17692710#17692710)

### error: Server does not allow request for unadvertised object

`git submodule update --force --recursive --init --remote`

[Why does git fail to fetch specific valid submodule for a given commit and how to fix it?](https://stackoverflow.com/questions/42417294/why-does-git-fail-to-fetch-specific-valid-submodule-for-a-given-commit-and-how-t)

Another solution is, fetching enough history from the server, so the commit is included in this history.

There are some options in `git fetch` can help you do this:

- `--deepen=<depth>`
- `--shallow-since=<date>`
- `--shallow-exclude=<revision>`

### Shallow clone a branch 

```
git clone --depth 1 https://path/to/repo/foo.git -b bar
```

Ref: [How do I shallow clone a repo on a specific branch?](https://stackoverflow.com/questions/21833870/how-do-i-shallow-clone-a-repo-on-a-specific-branch)

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

### sparse-checkout

turn on sparse-checkout: `git config core.sparseCheckout true`

What to check out is controlled by **.git/info/sparse-checkout**. 

```
/*
!**/test/**
```

The above example excludes all `test` directories from the checkout.

ref: [Is it possible to do a sparse checkout without checking out the whole repository first?](https://stackoverflow.com/questions/4114887/is-it-possible-to-do-a-sparse-checkout-without-checking-out-the-whole-repository), also [gitglossary  pathspec](https://git-scm.com/docs/gitglossary#gitglossary-aiddefpathspecapathspec)

### git orphan branch

`git checkout --orphan YourBranchName`

[How to create a new (and empty!) “root” branch?])(https://stackoverflow.com/questions/15034390/how-to-create-a-new-and-empty-root-branch)

### git for windows

* Line ending problem `git config --global core.autocrlf false`, [source](https://stackoverflow.com/questions/2016404/git-status-shows-modifications-git-checkout-file-doesnt-remove-them)

#### make a fold case sensitive in Windows 10

Window 10 introduces support for case sensitive folder, so that in such a folder "Hello.txt" and "hello.txt" are too different files.

You will need an admin cmd.exe and run `fsutil.exe file setCaseSensitiveInfo`, if your Winwodws doesn't support it yet, it will show `setCaseSensitiveInfo is an invalid parameter.`.

Otherwise, use `fsutil.exe file setCaseSensitiveInfo "full path to your folder" enable` to turn of case sensitivity on a folder.

> note that case sensitivity can not be inherited by sub folders.

ref: [Enable Case Sensitive Mode for Folders in Windows 10
](https://winaero.com/blog/enable-case-sensitive-mode-windows-10/)


###  [How to get the changes on a branch in Git](https://stackoverflow.com/questions/53569/how-to-get-the-changes-on-a-branch-in-git)

```
git diff HEAD...branch
git cherry branch [newbranch]
git diff --name-status branch [newbranch]
git diff `git merge-base feature-branch master` feature-branch
```

other refs:

* [Is there a way to see all changed files on a branch in Git?](https://stackoverflow.com/questions/6913263/is-there-a-way-to-see-all-changed-files-on-a-branch-in-git)
* [git diff showing only commits that revision/branch A is ahead of revision/branch B](https://stackoverflow.com/questions/17605208/git-diff-showing-only-commits-that-revision-branch-a-is-ahead-of-revision-branch)


### rewrite history

- [newren/git-filter-repo](https://github.com/newren/git-filter-repo/) is recommended over git-filter-branch and BFG.
- [Manual of git-filter-repo](https://htmlpreview.github.io/?https://github.com/newren/git-filter-repo/blob/docs/html/git-filter-repo.html)

Example

- `git filter-repo --invert-paths --path '.DS_Store' --use-base-name`

rewriting history may go wrong, should check the resulting history to confirm the effect.

## Git Client

* [tig](https://jonas.github.io/tig/). Text interface for Git repositories


## Git for Windows: HTTP Basic: Access denied and fatal Authentication

```
HTTP Basic: Access denied
```

[GitLab remote: HTTP Basic: Access denied and fatal Authentication](https://stackoverflow.com/questions/47860772/gitlab-remote-http-basic-access-denied-and-fatal-authentication)

## git show latest commits

`git log -10 --all --date-order`

For last 10 commits in all branches, you can do:

```
git log --graph --all --format=format:'%h - (%ai) %s — %cn %d' --abbrev-commit --date=relative -10
```

[How to find the latest commits in one git repository?](https://stackoverflow.com/questions/9678890/how-to-find-the-latest-commits-in-one-git-repository)

## git-lfs exclude sub-folders

```
*.asset filter=lfs diff=lfs merge=lfs -text
Assets/Resources/*.asset -filter=lfs -diff=lfs -merge=lfs -text
```

[How to make git LFS not apply to a subdirectory](https://stackoverflow.com/questions/45533593/how-to-make-git-lfs-not-apply-to-a-subdirectory)

[Git LFS track folder recursively](https://stackoverflow.com/questions/35769330/git-lfs-track-folder-recursively)


## pageant

- Use klink from Kitty, instead of plink from Putty. Klink has option "-auto-store-sshkey"
- Use GIT_SSH_COMMAND instead of GIT_SSH

GIT_SSH_COMMAND: `C:\\path\\to\\klink.exe -auto-store-sshkey`

or maybe

GIT_SSH_COMMAND: `C:/path/to/klink.exe -auto-store-sshkey`

## .netrc

.netrc can be used to provide HTTP basic asscess to git when accessing repo through http.

example .netrc:

```
machina gitlab.com/username/project login username password password_generated_by_gitlab_for_the_project
```

## noproxy

When a http_proxy is set, and you would like to by pass the proxy for some hosts:

```
no_proxy=localhost,127.0.0.0,127.0.1.1,127.0.1.1,local.home
```

see: [Setting up proxy to ignore all local addresses [duplicate]](https://askubuntu.com/questions/11274/setting-up-proxy-to-ignore-all-local-addresses)

## github access token

- [technoweenie/gist:1072829](https://gist.github.com/technoweenie/1072829)
- [Creating a personal access token for the command line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line)