If you have problems authenticating to the Tumblr network please have a look on the following common issues.

### Authenticate does not work / crash

If you experience crashes right before or while logging in, it may be that on your system the "[Visual C++ Redistributable 2015-2019](https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0)" ([x86](https://aka.ms/vs/16/release/vc_redist.x86.exe) or [x64](https://aka.ms/vs/16/release/vc_redist.x64.exe)) is missing. You can download it from MS.<br/>
Download and install the required package, then start TumblThree again and try to log in.

### Authenticate window shows a white screen

In rare cases the authenticate window opens, but shows a white screen instead of the Tumblr login page.<br/>
You can have a look at the Embedded Chromium debug.log file to see if you can find any hint at the end of the file. Else please write us through the [issues section](https://github.com/TumblThreeApp/TumblThree/issues/new/choose).

### Authenticate window hangs (no response)

Some users experience the problem that they cannot interact with authenticate window, it hangs or shows no response.<br/>
If you are using an Intel 11th Gen iris graphics cards then you'll need to update your driver.

### A different problem?

In case you experience other authentication problems not listed here or the recommendation doesn't solve it, please file an [issue report](https://github.com/TumblThreeApp/TumblThree/issues/new/choose).
