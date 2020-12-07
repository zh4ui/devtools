# macOS

## catalina


### xcrun: error:

`clang` shows:

`xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun`

fix it with: `xcode-select --install`

## Tools

* [deluge](https://deluge-torrent.org/), torrent client.
* [qBittorrent](https://www.qbittorrent.org/), torrent client.
* FileMerge, macos builtin for file comparison


## Tips

*Make Finder Search in Folder*

Open the Finder Preference, switch to the Advanced tab, on the dropdown list named `When performing a search`, select `Search the Current Folder`.

### remap key $

```
$ hidutil property --set '{"UserKeyMapping":[{"HIDKeyboardModifierMappingSrc":0x700000064,"HIDKeyboardModifierMappingDst":0x700000035}]}'
```

From [MacBook Keyboard Setup: The Mysterious § Key]:

> My first instinct was to put the command into a .sh file and add it to the Login items in the System Preferences of the Mac. I tried it but for some reason it didn’t start the next time I restarted. So I dug deeper and found out I had to create an Automator script and compile it to a binary (app) which I can then safely add to the Login items. A few minutes later I had the final solution :)

<https://github.com/dchakarov/restore-tilde>

- [MacBook Keyboard Setup: The Mysterious § Key]
- [ hidutil - looking for Usage ID of § key ](https://discussions.apple.com/thread/8133633)
- [Remap Caps Lock to Backspace in macOS Sierra in 1 Second](http://homeowmorphism.com/articles/17/Remap-CapsLock-Backspace-Sierra)
- [Remapping Keys in macOS 10.12 Sierra](https://developer.apple.com/library/archive/technotes/tn2450/_index.html)
- [HID Usage Tables 1.12](https://www.usb.org/document-library/hid-usage-tables-112)
- [hut1_12v2.pdf](https://www.usb.org/sites/default/files/documents/hut1_12v2.pdf)
- [USB human interface device class](https://en.wikipedia.org/wiki/USB_human_interface_device_class)
- [ MightyPork/usb_hid_keys.h](https://gist.github.com/MightyPork/6da26e382a7ad91b5496ee55fdc73db2)
- [USB ScanCodes](https://www.win.tue.nl/~aeb/linux/kbd/scancodes-14.html)
- [Karabiner-Elements](https://pqrs.org/osx/karabiner/)


[MacBook Keyboard Setup: The Mysterious § Key]: https://dchakarov.com/blog/macbook-remap-keys/

## Mojave

**Light window in dark theme (OS in dark, applications in light)**

```sh
defaults write -g NSRequiresAquaSystemAppearance -bool Yes
```

Log out and log in

**Screenshot**

Shift+CMD+5 to get into the screenshot mode

## QuickTime

**Rip Audio from Video**

Using QuickTime Player: File / Export / Audio Only

Source: [Rip audio file from video file in OSX](https://apple.stackexchange.com/questions/113125/rip-audio-file-from-video-file-in-osx) 
**Trim an MP3**

Using QuickTime Player: Edit / Trim


Source: [Trim an MP3 on your Mac](http://osxdaily.com/2010/09/16/trim-mp3-on-your-mac/) [A how-to guide for trimming MP3 audio in macOS Sierra using just the software that comes with your Mac.](https://biteable.com/blog/tips/trimming-audio-macos/)

## Safari

**Safari - How to enable local file access**

 * First you need to enable the develop menu.
 * Click on the Develop menu
 * Select Disable Local File Restrictions.

[source](https://ccm.net/faq/36342-safari-how-to-enable-local-file-access)

## Terminal.app

**Scroll to Previous Mark**

`CMD+UP`

**Dracula dark theme**

[A dark theme for Terminal.app and 50+ apps](https://draculatheme.com/terminal/)

## Finder

**show hidden files**

`CMD+SHIFT+.(dot)`

## Command line

* `otool` an llvm equivalent to objdump
* `hidutil` to dump iso.
  * Example: `hdiutil makehybrid -iso -joliet -o Image.iso /input_path`
  * Ref: [Mac OS X: Best Way to Make an ISO from a CD or DVD](https://superuser.com/questions/85987/mac-os-x-best-way-to-make-an-iso-from-a-cd-or-dvd)
* burn catalina to disk: `sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/Untitled`

## TimeMachine

[Types of disks you can use with Time Machine on Mac](https://support.apple.com/en-sg/guide/mac-help/mh15139/mac) says APFS can not be used for TimeMachine backup.

A big mistake I made, is to convert the HFS+ to APFS using `diskutil apfs convert diskxx`, even if it's not allowed in Disk Utility. 

> TimeMachine takes a lot of time to finish encrypting.

## Screen Sharing

macOS comes with Screen Sharing, for example:

* [VNC Server for Mac OS?](https://apple.stackexchange.com/questions/303647/vnc-server-for-mac-os)
* [How to remotely access & control a Mac desktop](https://www.macworld.co.uk/how-to/mac-software/remote-access-control-mac-3594139/)

You only need a VNC client to connect to the built-in server. Examples of such client:

* VNC Viewer from RealVNC
* TightVNC

However, the screen sharing seems to be slow. There are some third party servers can be used:

* TeamViewer, free for personal use
* NoMachine, has a free version with limited functionality

refs:

* [Getting started with NoMachine](https://www.nomachine.com/getting-started-with-nomachine)
* <https://en.wikipedia.org/wiki/Comparison_of_remote_desktop_software>

## brew

### openjdk

- https://github.com/AdoptOpenJDK/homebrew-openjdk

```
$ brew tap AdoptOpenJDK/openjdk
$ brew cask install adoptopenjdk14
```