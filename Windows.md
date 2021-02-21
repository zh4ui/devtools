# Windows

## Essentials

* [QTTabBar](http://qttabbar.wikidot.com/). Add tabs to your Windows Explorer.
* [Chocolatey](http://chocolatey.org/). A powerful package manager for windows.
* [Scoop](http://scoop.sh/). A lightweight package manager for windows. Install to user by default.

## Extra

* [QL-Win/QuickLook](https://github.com/QL-Win/QuickLook/). Bring macOS “Quick Look” feature to Windows.
* [DeskPins](http://efotinis.neocities.org/deskpins/index.html). DeskPins can be used to make any application topmost, that is, to keep it above all other windows. 
* [BaseX](http://www.basex.org/). A light-weight XML database suitable for desktop use.
* [yed](https://www.yworks.com/yed). A free effective graph editor by yWorks.
* [Sumatra PDF](https://www.sumatrapdfreader.org) a small, efficient PDF reader without fancy stuff. Works on large PDF files where Acrobat Reader DC fails short.
* [PDFsam](https://pdfsam.org/). Offer the functionality of splitting and Merging PDF pages. The basic version is free. Note that if you are using macOS, you can use Preview for the purpose.
* [GoldenDict](http://goldendict.org/). A dictionary client that supports many dictionary formats.
* WinMerge. A diff-merge tool for Windows.
* Link Shell Extension. Create NTFS hardlinks by using Context Menu.
* Microsoft Mathematics. A mathematic grapher provided by Microsoft.
* [XMLmind XML Editor Peronsal Edition](http://www.xmlmind.com/xmleditor/download.shtml). A XML editor provided by XMLmind.
* [UV Outliner](http://www.uvoutliner.com/). A Windows outliner.
* [poppler](https://poppler.freedesktop.org/). A set of PDF utilities, one of which is pdf2html that can help convert pdf to html.
* [coolwanglu/pdf2htmlEX](https://github.com/coolwanglu/pdf2htmlEX). Convert PDF to HTML without losing text or format.
* [paint.net](https://www.getpaint.net/). Definitely an enhancement to MS.Paint.
* [Keepass](https://keepass.info/). A password manager written in C#. Can be used as a elementary database. Support a lot of extensions.
* [PowerToys](https://github.com/microsoft/PowerToys), FancyZone is very interesting. Install it with `https://github.com/microsoft/PowerToys`

## Dev Tools

* [Google Protobuf](https://github.com/google/protobuf). Interface Description Language provided by Google. You can generate documents from Protobuf by using [protoc-gen-doc](https://github.com/pseudomuto/protoc-gen-doc). Uber has [some tools](https://github.com/uber/prototool) for Protobuf.
* [vcpkg](https://github.com/Microsoft/vcpkg). C++ Library Manager for Windows, Linux, and MacOS.
* [YAML](http://yaml.org/). YAML Ain't Markup Language.
* [TortoiseHG](https://tortoisehg.bitbucket.io/). A GUI client for Mercurial SCM.
* [royal ts](https://www.royalapplications.com/ts). A multi-hand connection manager.
* [NoMachine](https://www.nomachine.com/). Remote Desktop Software. VNC capable.
* [HxD](http://www.mh-nexus.de/). A hex editor for windows.
* [GitExtensions](https://github.com/gitextensions/gitextensions). Good Git GUI on Windows.
* [plantuml](http://plantuml.com/). Convert text descriptions to UML diagrams. A similiar tool is [Mermaid](https://github.com/knsv/mermaid)..
* [Kitty](http://kitty.9bis.net/). An enhanced PuTTY.
* [Chezmoi](https://github.com/twpayne/chezmoi) A dotfiles manager, written in Go. Support templating configuration files with Go's template system. Also support storing/fetching secrets to secret manageers (e.g. keepass, lastpass) before adding/applying templates.
* [dependency walker](http://www.dependencywalker.com/) A DLL dependency viewer
* [DLL Exprt View](http://www.nirsoft.net/utils/dll_export_viewer.html) displays the list of all exported functions and their virtual memory addresses for the specified DLL files.
* [DB Browser for SQLite](https://sqlitebrowser.org/), cross platform DB Browser for SQLite, [nightly build](https://nightlies.sqlitebrowser.org/latest/)
* [Adminer](adminer.org), a php based DB management tool
* [Adobe XD], a UI/UX design tool from Adobe.

## Tips

**Run cmd.exe for current folder**

* In *Windows Explorer*, Alt+D to locate the Address Bar, enter `cmd` to open `cmd.exe` in current folder.
* Shift + right click on a folder, select `Open command windows here` 

**RTF file format**

RTF file format can be useful in Windows. It's lighter than word, but support Rich Text. Windows has a built-in application called WordPad to open and edit RTF files. Addtionally, it can be previewed in Windows Explorer's preview panel. 

**Find RAM Type**

```cmd
wmic memorychip list full
```

from [How to find the RAM type in command prompt?](https://superuser.com/questions/606318/how-to-find-the-ram-type-in-command-prompt)

**Encryption**

* bitLocker can be used to encrypt the whole disk
* EFS can be used to encrpyt individual files

## System Management

**List Explorer Extensions**

[Autoruns](https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns) from Sysinternals (Microsoft).

[Source](https://superuser.com/questions/286000/how-to-list-explorer-extensions-and-disable-them).

**cleanup Component Store**

Run: `dism.exe /Online /Cleanup-Image /AnalyzeComponentStore`

If `Component Store Cleanup Recommended : Yes`, run: `dism.exe /online /Cleanup-Image /StartComponentCleanup`

source: [腾出 C 盘又一方法，查看和清理 Windows 10「组件存储」](https://www.sysgeek.cn/windows-10-clean-component-store/)

**VHD Creation**

Win10: Win+X to open open user menu and then select Computer Management. Under Storage, right click Disk Management and click "Create VHD".

**Exlude folder from Windows Defender**

[Add an exclusion to Windows Security](https://support.microsoft.com/en-us/help/4028485/windows-10-add-an-exclusion-to-windows-security)

### Startup folder

`%APPDATA%Microsoft\Windows\Start Menu\Programs\Startup`

or 

`shell:startup`


All user startup

`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`

or 

`shell:common startup`

## WSL

### enable apt proxy in sudo mode

[Setting up apt-get to use a http-proxy](https://help.ubuntu.com/community/AptGet/Howto#Setting_up_apt-get_to_use_a_http-proxy)

Add following lines to /etc/sudoers:

```
Defaults env_keep = "http_proxy https_proxy ftp_proxy"
```

then export your proxies in shell.
