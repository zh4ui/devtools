# Ubuntu 18.04 LTS Bionic Beavor

## tips

* packages can be found on `https://launchpad.net/ubuntu`

## tools

* [Visual Studio Code](https://code.visualstudio.com/docs/setup/linux)
    * You may want to go to File>Preference>Settings and in user settings and set  "window.titleBarStyle": "native",

### LLVM

LLVM's deb packages are available at `https://apt.llvm.org/`

Add `llvm.list` to `/etc/apt/sources.list.d` with following content:

```
deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic-7 main
```

```
 wget -O - http://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
```

GPG error: http://apt.llvm.org/cosmic llvm-toolchain-cosmic-7 InRelease

[Error getting access to LLVM Debian/Ubuntu nightly packages](https://askubuntu.com/questions/895786/error-getting-access-to-llvm-debian-ubuntu-nightly-packages)

