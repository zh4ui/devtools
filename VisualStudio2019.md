# VisualStudio 2019


## CMake Support

* [CMake projects in Visual Studio](https://docs.microsoft.com/en-us/cpp/build/cmake-projects-in-visual-studio?view=vs-2019)
* [2016: CMake support in Visual Studio](https://devblogs.microsoft.com/cppblog/cmake-support-in-visual-studio/)

## Extensions

* [FileNesting](https://github.com/madskristensen/FileNesting), nesting file in SolutionExplorer

## Tips

* [Visual Studio Tip #8: Adding existing files with Show All Files](https://blogs.msdn.microsoft.com/benwilli/2015/05/21/visual-studio-tip-8-adding-existing-files-with-show-all-files/)
* [How To Create an Icon for Visual Studio with just MSPaint and Visual Studio](https://stackoverflow.com/questions/40933304/how-to-create-an-icon-for-visual-studio-with-just-mspaint-and-visual-studio)

### Clear Nudget Cache

```
dotnet nuget locals all --clear
```

- [How to clear NuGet package cache using command line?](https://stackoverflow.com/questions/30933277/how-to-clear-nuget-package-cache-using-command-line)
- [Managing the global packages, cache, and temp folders](https://docs.microsoft.com/en-us/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [NuGet frequently-asked questions](https://docs.microsoft.com/en-us/nuget/resources/nuget-faq)

### Disable IntelliSense

- [Disable or pause default IntelliSense for C/C++](https://docs.wholetomato.com/default.asp?W133)
- [Visual Studio: How to Turn Off Autocomplete](https://www.technipages.com/visual-studio-turn-off-autocomplete)

## Add VS2019 community command line prompt to Windows Terminal

[Add Developer Command Prompt for Visual Studio to Windows Terminal?](https://stackoverflow.com/questions/57925428/add-developer-command-prompt-for-visual-studio-to-windows-terminal)

```json
    {
      "guid": "{1748ecca-abdd-4aa4-bcc4-9fca0d045be5}",
      "name": "VS cmd x64",
      "cursorShape": "filledBox",
      "commandline": "%comspec% /k \"C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\Community\\VC\\Auxiliary\\Build\\vcvars64.bat\"",
      "icon": "ms-appx:///ProfileIcons/{0caa0dad-35be-5f56-a8ff-afceeeaa6101}.png",
      "hidden": false
    }

```