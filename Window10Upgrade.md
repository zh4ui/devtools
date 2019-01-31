# Upgrade to Window 10 

## tips

* [How To Enable Delete Confirmation Dialog In Windows 10/8.1](https://www.intowindows.com/how-to-enable-delete-confirmation-dialog-in-windows-8/)
* backup & restore chrome user data
  * open `"%LOCALAPPDATA%\Google\Chrome\User Data\`, backup directory `default`
  * resotre `default`
* backup & restore firefox user data
  * open `%APPDATA%\Mozilla\Firefox\Profiles\`, backup directory `*.default`
  * resotre previous content from `*.default` to new `*.default`


## shortcuts

* `Win-x` to open a system menu
* In “Run” box, type cmd and press Ctrl+Shift+Enter to run it in Admin. [source](https://www.howtogeek.com/194041/how-to-open-the-command-prompt-as-administrator-in-windows-8.1/)


## Issues

### DPI Scaling on legacy APPS

If you are using multiple monitors, chances are you will experience blurry text on one of the monitors, especially when different DPI scalings are set in Display Settings.

One way to fix it is follow [How to use DPI scaling in Windows 10 to fix blurry old apps](https://www.windowscentral.com/how-improve-app-dpi-scaling-enabling-system-enhanced-feature-windows-10):

* Open the app you want to enhance scaling. Right-click the app in the taskbar.
* Right-click the name of the app and select Properties.
* Click the Compatibility tab.
* Under "Settings," check the Override high DPI scaling behavior option.
* Under "Scaling performed by" drop-down menu, select System (Enhanced).

> Quick Tip: You can also find the app's .exe file, right-click it, and select Properties.

Other Refs:

* [Improving the high-DPI experience in GDI based Desktop Apps](https://blogs.windows.com/buildingapps/2017/05/19/improving-high-dpi-experience-gdi-based-desktop-apps/)
* [High-DPI Scaling Improvements for Desktop Applications in the Windows 10 Creators Update (1703)](https://blogs.windows.com/buildingapps/2017/04/04/high-dpi-scaling-improvements-desktop-applications-windows-10-creators-update/#DuYXCkR0fhvpsMDE.97)

However, the above trick doesn't work for Office Applications, e.g. Word, Outlook. For these apps, according to [Office support for high definition displays](https://support.office.com/en-us/article/office-support-for-high-definition-displays-6720ca0e-be59-41f6-b629-1369f549279d), you will have to update your Windows to (1803) update, and then try the display settings in apps' menu: `File > Options > General`.