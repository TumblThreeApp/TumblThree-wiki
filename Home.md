<img align="left" width="60" height="60" src="wiki/images/tumblthree_icon.png" alt="TumblThree Logo">

# TumblThree - A Tumblr and Twitter Blog Backup Application

TumblThree is a free and open source Tumblr and Twitter blog backup application. It downloads photo, video, audio and text posts from a given blog.<br/>
It is the code rewrite of [TumblTwo](https://github.com/johanneszab/TumblTwo), using the [Win Application Framework (WAF)](https://github.com/jbe2277/waf) and C# with WPF and the MVVM pattern.

</br>
</br>

<p align="center"><img src="images/tumblthree.png" width="75%" align="center" alt="TumblThree Main UI"></p>

## Features:

* Source code at GitHub (written in C# using WPF and MVVM)
* Multiple concurrent downloads of a single blog and/or different blogs
* A clipboard monitor that detects *blogname.tumblr.com* urls in the clipboard (copy and paste) and automatically adds the blog to the bloglist
* A settings panel (change download location, turn preview off/on, define number of concurrent downloads, set the imagesize of downloaded pictures, set download defaults, enable portable mode, etc.)
* An option to skip the download of a file if it has already been downloaded before in any currently added blog
* Preview of photos & videos
* File rename functionality
* Download of Twitter/X blogs
* Image viewer with slideshow mode
* Automated update process
* Group blogs into collections
* :star: Download of Bluesky (user feed) blogs 🆕
<details>
  <summary>click for more</summary><br/>

* Download of Gif instead of WebP/Gifv images from Tumblr
* Internationalization support (several languages available)
* A download queue
* Autosave of the queuelist
* Save, clear and restore the queuelist
* Uses Windows proxy settings
* A bandwidth throttler
* An option to download an url list instead of the actual files
* Set of a start time for a automatic download (e.g. during nights)
* Change of blog settings of multiple selected blogs at once
* Uses SSL connections
* Taskbar buttons and key bindings
* Choice of download format for .pnj links
</details>

### Backup/download of <sub><sup>(click names to expand)</sup></sub>
* <details><summary><b>Blogs / Hidden blogs</b></summary>

  * Download of photo, video (only tumblr.com hosted), text, audio, quote, conversation, link and question posts
  * Download meta information for photo, video and audio posts
  * Download inlined photos and videos (e.g. photos embedded in question&answer posts)
  * Download of all image sizes possible (SVC, API only for newer blogs, higher resolution not possible for old blogs *1)
  * Support for downloading Imgur, Gfycat, Webmshare, Uguu and Catbox linked files in tumblr posts
  * Download of safe mode/NSFW blogs
  * Allows to download only original content of the blog and skip reblogged posts
  * Can download only tagged posts
  * Can download only specific blog pages instead of the whole blog
  * Allows to download blog posts in a defined time span
  * Can download hidden blogs (login required / dash board blogs)
  * Can download password protected blogs (of non-hidden blogs)
  </details>
* <details><summary><b>Liked/by and Likes</b></summary>

  * A downloader for downloading "liked by" (e.g. https://www.tumblr.com/liked/by/wallpaperfx/) and "likes" (e.g. https://www.tumblr.com/likes) photos and videos instead of a tumblr blog (login required)
  * Download of all image sizes possible (SVC, API only for newer blogs, higher resolution not possible for old blogs *1)
  * Allows to download posts in a defined time span
  
  </details>
* <details><summary><b>Tumblr searches</b></summary>

  * A downloader for downloading photos and videos from the tumblr search (e.g. http://www.tumblr.com/search/my+keywords)
  * Download of all image sizes possible (SVC, API only for newer blogs, higher resolution not possible for old blogs *1)
  * Can download only specific blog pages instead of the whole blog
  
  </details>
* <details><summary><b>Tumblr tag searches</b></summary>

  * A downloader for downloading photos and videos from the tumblr tag search (e.g. http://www.tumblr.com/tagged/my+keywords) (login required)
  * Download of all image sizes possible (SVC, API only for newer blogs, higher resolution not possible for old blogs *1)
  * Allows to download posts in a defined time span
  
  </details>
* <details><summary><b>Twitter/X Blogs</b></summary>

  * Download of photo, video and text posts of blogs
  * Download meta information for photo and video posts
  * Allows to download only original content of the blog and skip reblogged posts
  * Can download only tagged posts
  * Allows to download blog posts in a defined time span
  
  </details>
* <details><summary><b>Bluesky Blogs</b></summary>

  * Download of photo, video and text posts of blogs
  * Download meta information for photo and video posts
  * Allows to download only original content of the blog and skip reblogged posts
  * Can download only tagged posts
  * Allows to download blog posts in a defined time span

  </details>

_*1 [Tumblr raw image files are inaccessible as of August 10, 2018](https://github.com/johanneszab/TumblThree/issues/261)_

## Download:

Latest versions can be found [here](https://github.com/TumblThreeApp/TumblThree/releases).

Please keep in mind that probably only the latest version is functioning properly since the platforms evolve and from time to time change their data structures which makes changes in TumblThree necessary again. So update your application regularly.

## Application Usage and Getting Started

Read our wiki page about [Application Usage](wiki/How-to-use-the-Application).

The default settings should cover most users. You should only have to change the download location and the kind of posts you want to download. You can find more information in [Getting Started](wiki/Getting-Started) and [Insights](wiki/Insights).

## Feedback and Bug Reports

If you like TumblThree, give it a star <img src="wiki/images/star.png" alt="star" height="16"/> (at the right upper corner of the page)!

**You are welcome to participate in [Discussions](https://github.com/TumblThreeApp/TumblThree/discussions) (our Forum).** If you don't have a GitHub account yet, please sign up for one, it is free.<br>
We appreciate it, if you send us your feedback or file a bug report. Preferably, just fill out a [Bug report](https://github.com/TumblThreeApp/TumblThree/issues/new/choose). 

In case you don't like to register an account for some reason, but still want to provide feedback or a bug report, use the following web form:
[tumblthreeapp.github.io/TumblThree/feedback.html](https://tumblthreeapp.github.io/TumblThree/feedback.html)

## Contributing to TumblThree

We like the [all-contributors](https://allcontributors.org/) specification. Contributions of any kind are welcome!
If you've ever wanted to contribute to open source, and a great cause, now is your chance!

* You can find useful information about How and What you can contribute to the TumblThree project [here](https://github.com/TumblThreeApp/TumblThree/blob/master/Contributing.md).
* Also see the [wiki page for ideas of new or missing features](wiki/New-Feature-Requests-and-Possible-Enhancements) and add your thoughts.

## Contributors ✨

Last but not least see also the [list of contributors](https://github.com/TumblThreeApp/TumblThree/blob/master/docs/Contributors.md) who participated in this project.
