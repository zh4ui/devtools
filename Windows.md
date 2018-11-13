# Windows

## Tools

* [QL-Win/QuickLook](https://github.com/QL-Win/QuickLook/). Bring macOS “Quick Look” feature to Windows.
* [DeskPins](http://efotinis.neocities.org/deskpins/index.html). DeskPins can be used to make any application topmost, that is, to keep it above all other windows. 
* [BaseX](http://www.basex.org/). A light-weight XML database suitable for desktop use.
* [TortoiseHG](https://tortoisehg.bitbucket.io/). A GUI client for Mercurial SCM.
* [plantuml](http://plantuml.com/). Convert text descriptions to UML diagrams. A similiar tool is [Mermaid](https://github.com/knsv/mermaid)..
* [QTTabBar](http://qttabbar.wikidot.com/). Add tabs to your Windows Explorer.
* [yed](https://www.yworks.com/yed). A free effective graph editor by yWorks.
* [Sumatra PDF](https://www.sumatrapdfreader.org) a small, efficient PDF reader without fancy stuff. Works on large PDF files where Acrobat Reader DC fails short.
* [PDFsam](https://pdfsam.org/). Offer the functionality of splitting and Merging PDF pages. The basic version is free. Note that if you are using macOS, you can use Preview for the purpose.
* [GoldenDict](http://goldendict.org/). A dictionary client that supports many dictionary formats.
* WinMerge. A diff-merge tool for Windows.
* Link Shell Extension. Create NTFS hardlinks by using Context Menu.
* Microsoft Mathematics. A mathematic grapher provided by Microsoft.
* [GitExtensions](https://github.com/gitextensions/gitextensions). Good Git GUI on Windows.
* [XMLmind XML Editor Peronsal Edition](http://www.xmlmind.com/xmleditor/download.shtml). A XML editor provided by XMLmind.

## Dev Tools

* [Google Protobuf](https://github.com/google/protobuf). Interface Description Language provided by Google. You can generate documents from Protobuf by using [protoc-gen-doc](https://github.com/pseudomuto/protoc-gen-doc). Uber has [some tools](https://github.com/uber/prototool) for Protobuf.
* [vcpkg](https://github.com/Microsoft/vcpkg). C++ Library Manager for Windows, Linux, and MacOS.
* [YAML](http://yaml.org/). YAML Ain't Markup Language.


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


## System Management

**List Explorer Extensions**

[Autoruns](https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns) from Sysinternals (Microsoft).

[Source](https://superuser.com/questions/286000/how-to-list-explorer-extensions-and-disable-them).