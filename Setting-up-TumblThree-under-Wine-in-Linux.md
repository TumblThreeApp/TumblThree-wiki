The examples I'm giving are from `Ubuntu Noble (24.04 LTS)` using the Mate desktop environment. There are probably no real differences for the standard Ubuntu desktop and very similar for most Debian distributions.

If you're using some distributions your package manager may be something else than `apt` like `dnf` or `pacman` or `yum`. Your library names may also be slightly different.

## Install Wine

Wine allows you to run some Windows applications under Linux or MacOS.

There may be a version of Wine available through your package manager, but it may be out of date. WineHQ recommends installing a newer release. See the WineHQ Download page for instructions on adding the repository and signing keys if needed. Briefly, the following commands work on Ubuntu:

```bash
# enable i386 architecture since it's often required for wine
# even if running a 64-bit application
sudo dpkg --add-architecture i386

# just in case it's not installed
sudo apt install wget

# add more up-to-date wine repo to sources for updating
sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/$(lsb_release -sc)/winehq-$(lsb_release -sc).sources

# update your package manager list of software
sudo apt update

# install wine
sudo apt install --install-recommends winehq-stable winetricks cabextract unzip p7zip-full
```

## Create a clean prefix for TumblThree

This creates a specific clean environment for TumblThree separate from the main prefix, which might change if you configure other Windows settings for other programs.

```bash
# set environment variables for this environment, if you open and close your
# terminal or start a new window or tab then you'll need to set these environment
# variables again each time.  At the end we'll set them in a shell script.
export WINEPREFIX="$HOME/.wine-tumblthree"
export WINEARCH=win64

wineboot -u
```

## Install some base settings and libraries in your Wine prefix

```bash
# install these with winetricks
winetricks -q settings win10
winetricks -q corefonts
winetricks -q dotnet48

winetricks -q dotnetcore3
winetricks -q dotnetcoredesktop3
winetricks -q d3dcompiler_47
winetricks -q d3dx9
```

## Install WebView2

Without WebView2 installed, the authentication screen may not work and some
kinds of crawling may not work.

Download it manually by going to the [WebView2 Download page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/consumer/?cs=1301686474&form=MA13LH).

You want to download the full Evergreen standalone installer (not the small bootstrapper). To do that, click the "Go to page" button next to the text "Are you an administrator for your organization? Visit the WebView2 developer page." Then choose the "Evergreen Standalone Installer" for your processor architecture (probably x64), accept the terms, and download the full installer.

```bash
# change to the location where you downloaded
cd ~/Downloads

# run wine and run the installer, the filename may be slightly different depending on architecture
wine MicrosoftEdgeWebView2RuntimeInstallerX64.exe
```

Wait for the window to appear and click through the installer.

If you receive a message that your installer is incompatible with your version of Windows, then type
`winecfg` and in the window that comes up click the "applications" tab
and choose windows version like `Windows 10` at the bottom
and click 'ok' and run the installer again until it installs.

## Download and extract TumblThree

Go to the [versions downloads page for TumblThree](https://github.com/TumblThreeApp/TumblThree/releases) and download for your architecture (probably x64).

Extract it where you'd like to run the program, for example:

```bash
cd ~/Downloads
mkdir ~/tumblthree
unzip TumblThree-v2.20.1-x64-Application.zip -d ~/tumblthree
```

I just put it in my home directory, but you can put it in `/usr/local` or
somewhere else if you wish.

## Run TumblThree

Test to see if it works.   Mine would not work under Windows 10 settings and the screen never opened.

I hit ctrl-c to terminate and instead typed
`winecfg`.

In the window that comes up click the "applications" tab
and choose `Windows 7` at the bottom and click 'ok'

```bash
cd ~/tumblthree
wine TumblThree.exe
```

## Setting up the application and being sure it functions

### If you get a warning that "TumblThree is in a protected folder"

You can add a drive mapping for the virtual Windows directory structure 
(or see how it's mapped) to your linux file system by typing `winecfg`
and going to the `Drives` tab.

Then run `wine TumblThree.exe` again, go to `Settings` and then click
`Browse` next to the `Download location` and select the directory where
you'd like to save files.

### Be sure webview works correctly

WebView2 allows you to log in and is needed for some kinds of crawling.

Go to `Settings` and click the `Connection` tab and click `Authenticate`
next to `Tumblr`. It brings up a page where you can log in. If this page
displays then WebView2 is probably working.

I originally tested with other versions of dot net and this was always a
blank white screen and never showed a web page. The dependencies
I installed and setting the Windows version to Windows 7 fixed this
so it worked for me.

If not, then use web searches or LLMs to suggest additional command line settings that *might* work around the blank-screen problem for WebView2 under Wine.
It may also depend on your graphics drivers from what I understand.


### Setting up an easy way to start TumblThree with the correct prefix

In the application directory, type `nano start_tumblthree.sh`.

Put the following contents in the file and then save and close it.

```bash
#!/bin/bash
export WINEPREFIX="$HOME/.wine-tumblthree"
export WINEARCH=win64
wine TumblThree.exe
```

Type `chmod u+x start_tumblthree.sh` to give it executable permissions.

Then cd to the directory and type `./start_tumblthree.sh` when you want to run it.
