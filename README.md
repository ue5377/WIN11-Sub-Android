# Rooted WSA (Windows Subsystem For Android) with Google Apps for Windows 11

## Features
- Integrated Magisk and OpenGApps
- No Linux environment required for integration
- Simple installation process
- Support both ARM64 and x64
- Support all OpenGApps variants except for aroma (aroma does not support x86_64, please use super instead)
- Fixed external storage access of "DocumentUI"
- (NOT WORKING YET, will be updating the repo insteaqd upon updates) In the Future, Should update automatically without losing root
- Automatically activates "Developer mode" in Windows 11 settings during install
- Update to new version while preserving data with one-click script
- Merged all language packs
- Support for managing start menu icons (you will have to manually install "WSAHelper". - Link here - https://github.com/LSPosed/WSAHelper/releases/latest


## Detailed Guide

----Please Watch, Star and Fork if you'd like to support and help with Development, Thanks!----

Step One- Download.

Step Two- Right-click `Install.ps1` and select `Run with PowerShell`
    NOTE!*** --- If you previously have a ROOTED WSA installation, it will automatically uninstall the previous and **preserve all userdata** and install the new one.
    - If you have an OFFICIAL WSA installation, you MUST uninstall it first. (If you want to preserve your data, you need to backup the data in this location - [%LOCALAPPDATA%\Packages\MicrosoftCorporationII.WindowsSubsystemForAndroid_8wekyb3d8bbwe\LocalCache\userdata.vhdx] - You can restore it later. 
    
    Trouble-Shooting/Known Issues
    - If the popup windows disappears **without asking administrative permission** and WSA is not installed successfully, you should manually run `Install.ps1` as administrator, heres how:
        1. Press Win(Start)+X & select "Windows Terminal (Admin)"
        2. In the Terminal, Type `cd and navigate to the directory where you downloaded the Rooted WSA and press `enter`NOTE - to find your downloaded file easier try renaming it something easy for you to type/remember. Also try putting the download on a different drive then your OS, No idea why but it helped me get Powershell to find it.
        3. Input `PowerShell.exe -ExecutionPolicy Bypass -File .\Install.ps1` and press `enter`
        4. The script will run and WSA will be installed
        5. If this workaround does not work, then you PC simply doesnt meet the system requirements for WSA (im working on a bypass/Fix,No ETA, but it can be done in the registry, if you are comfortable doing it yourself let me know)
1. Magisk/Play store will be launched. Enjoy by installing LSPosed-zygisk with zygisk enabled or Riru and LSPosed-riru

## FAQ
- Can I delete the unzipped folder?

   NO! If you do youll completely delete WSA.
   
   
- Why does the size of the zip does not match the one shown?

   The zip you downloaded is compressed and Github is showing the uncompressed size.
   
   
- How can I update WSA to new version?

    For now, Find the Updated version on this Github, This is the ONLY place ill be uploading it. In the Future, it will be self updating.
    
    
- How can I get the logcat from WSA?

   Navigate here - `%LOCALAPPDATA%\Packages\MicrosoftCorporationII.WindowsSubsystemForAndroid_8wekyb3d8bbwe\LocalState\diagnostics\logcat`


- VPN is not working?

    Tell Microsoft to fix it. Seems they are doing it on purpouse. Or make a mod. 


- How to pass safetynet?

    Like all the other emulators, its not possible.(Yet)
    
    
- Virtualization is not enabled?

    `Install.ps1` helps you enable it - if not enabled, After rebooting, rerun `Install.ps1` to install WSA. If it's still not working, you have to enable virtualization in BIOS, if its even possible for your system.
    
    
- How to remount system as read-write?

    No yet possible in WSA since it's mounted as read-only by Hyper-V. You can modify system by making a Magisk module. Or directly modify system.img.
    
    
- `adb connect localhost:58526` Not working?

    Make sure developer mode is enabled. If the issue persists, check the IP address of WSA in the setting page and try `adb connect ip:5555`.
    
    
- Magisk online module list is empty?

    Magisk actively remove online module repository. You can install module locally or by `adb push module.zip /data/local/tmp` and `adb shell su -c magisk --install-module /data/local/tmp/module.zip`.
    
    
- Can I use Magisk 23.0 stable or lower version?

    No. Magisk has bugs preventing itself running on WSA. Magisk 24+ has fixed them. So you must use Magisk 24 or higher version.


- How can I get rid of Magisk?

    Choose `none` as root solution.
    
    
- I forked this project but Github Action script is updated, how can I synchronize it?

    1. In your fork repository, click `fetch upstream`
        ![fetch](https://docs.github.com/assets/cb-33284/images/help/repository/fetch-upstream-drop-down.png)
    1. Then and click `fetch and merge`
        ![merge](https://docs.github.com/assets/cb-128489/images/help/repository/fetch-and-merge-button.png)

FOR DEVELOPMENT AND RESEARCH PURPOUSES ONLY - NOT FOR SALE OR REDISTRIBUTION - WE TAKE NO RESPONSIBILITY FOR ANY DAMAGES, HARM OR ANYOTHER UNFORSEEN EVENT ARISING FROM THE USE OF THIS SOFTWARE - BY USING THIS SOFTWARE YOU AGREE TO RELEASE ALL LIABILITY TO ITS CREATORS - THIS IS AND ALWAYS WILL BE A FREE, OPEN-SOURCE PROJECT.



## Credits
- [Magisk](https://github.com/topjohnwu/Magisk): The most famous root solution on Android
- [The Open GApps Project](https://opengapps.org): One of the most famous Google Apps packages solution
- [WSA-Kernel-SU](https://github.com/LSPosed/WSA-Kernel-SU) and [kernel-assisted-superuser](https://git.zx2c4.com/kernel-assisted-superuser/): The kernel `su` for debugging Magisk Integration
- [WSAGAScript](https://github.com/ADeltaX/WSAGAScript): The first GApps integration script for WSA
