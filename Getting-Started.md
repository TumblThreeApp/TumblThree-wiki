The default settings should cover most users. You should only have to change the download location and the kind of posts you want to download. For this, in the Settings (click on the Settings button in the lower panel of the main user interface) you might want to change:
* General -> Download location: Specifies where to download the files. The default is in a folder _Blogs_ relative to the TumblThree.exe
* Blog -> Settings applied to each blog upon addition:
  * Here you can set what posts newly added blogs will download per default. To change what each blog downloads, click on a blog in the main interface, select the Details Tab on the right and change the settings. This separation allows to download different kind of post for different blogs. You can change the download settings for multiple existing blogs by selecting them with shift+left click for a range or ctrl-a for all of them.
  * Note: You might want to always select:
    *  _Download Reblogged posts_: Downloads reblogs, not just original content of the blog author.
    *  _Force Rescan_: Force Rescan always crawls the whole blog and not just new posts which were added after the last successful crawl. The statistics of a blog (total posts, number of post, number of duplicates) currently can only be updated if the whole blog is crawled. Thus, disabling this might result in downloading "more" posts than displayed in TumblThree. If you don't care about the displayed blog statistics, turning Force Rescan off will decrease the scanning time since already downloaded posts are skipped in the scanning.

Settings you might want to change if the download speed is not satisfactory:
* Connection -> Concurrent connections: Specifies the number of connections used for downloading posts. The number is shared between all actively downloading blogs.
* Connection -> Concurrent video connections: Specifies the number of connections used for downloading tumblr video posts. The vt.tumblr.com host regularly closes connections if the number is too high. Thus, the maximum number of vt.tumblr.com connections can be specified here independently.
* Connection -> Concurrent blogs: Number of blogs to download in parallel.

Most likely you don't have to change any of the other connection settings. In particular, settings you should never change, unless you're sure you know what you are doing:
* Connection -> Limit Tumblr Api Connections: Leave this checkbox checked and do not change the corresponding values of 90 connections per 60 seconds. If you still change them, you might end up with offline blogs or missing downloads.
