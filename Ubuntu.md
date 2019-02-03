# Ubuntu 18.04 LTS Bionic Beavor

## tips

* packages can be found on `https://launchpad.net/ubuntu`

## tools

* [Visual Studio Code](https://code.visualstudio.com/docs/setup/linux)
  * You may want to go to File>Preference>Settings and in user settings and set  "window.titleBarStyle": "native",
* [LXTerminal](the terminall app from LXDE, very lightweight)

### LLVM

LLVM's deb packages are available at `https://apt.llvm.org/`

Add `llvm.list` to `/etc/apt/sources.list.d` with following content:

```
deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic-7 main
```

If you encounter **GPG error: http://apt.llvm.org/cosmic llvm-toolchain-cosmic-7 InRelease**, import the key:

```
 wget -O - http://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
```


[Error getting access to LLVM Debian/Ubuntu nightly packages](https://askubuntu.com/questions/895786/error-getting-access-to-llvm-debian-ubuntu-nightly-packages)

### Vim 8

[How can I get a newer version of Vim on Ubuntu?](https://vi.stackexchange.com/questions/10817/how-can-i-get-a-newer-version-of-vim-on-ubuntu)

```
sudo add-apt-repository ppa:jonathonf/vim
sudo apt update
sudo apt install vim
```