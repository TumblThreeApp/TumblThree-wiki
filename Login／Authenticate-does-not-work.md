If you have problems authenticating to the Tumblr network please have a look on the following common issues.

## TumblThree 2.9.0 / 2.9.1

### Authenticate window shows a white screen

If the authenticate window opens, but shows a white screen instead of the login page, verify that you have the "[MS Edge Webview2 Runtime](https://go.microsoft.com/fwlink/p/?LinkId=2124703)" installed. If you have your installation folder in a protected location (e.g. "Program Files"), you should either create and give write access to the subfolder "TumblThree.exe.WebView2" or just use a newer version.

## TumblThree up to version 2.8.3

### Authenticate does not work / crash

If you experience crashes right before or while logging in, it may be that on your system the "[Visual C++ Redistributable 2015-2022](https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0)" ([x86](https://aka.ms/vs/17/release/vc_redist.x86.exe) or [x64](https://aka.ms/vs/17/release/vc_redist.x64.exe)) is missing. You can download it from Microsoft.<br/>
Download and install the required package, then start TumblThree again and try to log in.

### Authenticate window shows a white screen

In rare cases the authenticate window opens, but shows a white screen instead of the Tumblr login page.<br/>
You can have a look at the Embedded Chromium debug.log file to see if you can find any hint at the end of the file. Else please write us through the [issues section](https://github.com/TumblThreeApp/TumblThree/issues/new/choose).

### Authenticate window hangs (no response)

Some users experience the problem that they cannot interact with authenticate window, it hangs or shows no response.<br/>
If you are using an Intel 11th Gen iris graphics cards then you'll need to update your driver.

### A different problem?

In case you experience other authentication problems not listed here or the recommendation doesn't solve it, please file an [issue report](https://github.com/TumblThreeApp/TumblThree/issues/new/choose).
