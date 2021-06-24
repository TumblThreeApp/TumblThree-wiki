## Ideas to include/enhance the application ##

* Parse Options from the commandline and add non-UI mode.

* Maybe add 500px, instagram, flickr, pinterest or other tumblr similar pages?

* Redesign the UI layout and the controls.

* Implement a filesystem watcher that reads .txt files from a user-definable folder with new instructions. E.g. download blog X with tags Y now.

* Integration of an auto-updater

* Theme support.

* Move the blog index (i.e. .tumblr) files to a separate, user definable folder?

* Linux (G)UI

## Code Enhancements ##
Possible things to improve.

* Code refactoring.
* Unit tests.
* Documentation (code, user manuals, web page).
* Redesign and clean up the database structures?
  * We could implement a FolderBrowser that allows to browse through the filesystem from the main user interface, thus working like a FTP client. It loads and updates the blog manager with the databases found in the corresponding directory and you can submit them to the queue.
* Use more events driven code, for example in the AbstractDownloader.cs
* In the AbstractDownloader.cs and Crawler classes, use TPL Dataflow/Actor model instead of creating a huge list of Tasks using a blockingcollection/getconsumingenumerable.
* Use HttpClient instead of HttpWebRequests for downloading.
* Better handling of the [TimeoutExceptions](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Applications/Extensions/TaskTimeoutExtension.cs) that were introduced to terminate dead connections in wonky internet connections. I.e. notify the user that a connection dropped and act accordingly.
* ..

## How to add new website crawler ##

It should be quite straight forward now to add new sites like 500px, instagram, or twitter.
The downloader and most of the UI should be able to take different websites.

You can check [this commit](https://github.com/johanneszab/TumblThree/commit/efc9d903f49864ef1424b5496fabce0f0780a68d) for my addition of the  Tumblr tag search downloader for the most recent example. Older examples include the [Tumblr liked-by downloader](https://github.com/johanneszab/TumblThree/commit/d11375407f462e32ac3ccacb03e7b0861bbaaa39), the [Tumblr downloader for private blogs](https://github.com/johanneszab/TumblThree/commit/8ed1e11efc7c110931b29147460acfe814d4dc84) and the [Tumblr search downloader](https://github.com/TumblThreeApp/TumblThree/commit/cd6383749d28151c49cb3b59f16434f76bf84bfb). 

In essence, you have to do:

* Implement the [ICrawler interface](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Applications/Crawler/ICrawler.cs) and override the Crawl method to start the crawler and a DownloadBlogAsync task from the IDownloader interface. [See here](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Applications/Crawler/TumblrTagSearchCrawler.cs#L38) for an example implementation in the TumblrTagSearchCrawler.
* The [url validator](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Domain/Models/Validator.cs) needs adjustments to detect proper urls.
* Add your [BlogType](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Domain/Models/BlogTypes.cs).
* Add your Crawler to the [CrawlerFactory](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Applications/Crawler/CrawlerFactory.cs).
* Add your BlogType to the [BlogFactory](https://github.com/TumblThreeApp/TumblThree/blob/master/src/TumblThree/TumblThree.Domain/Models/BlogFactory.cs).
* You might want to add a new DetailsView.cs if you want different checkboxes or statistics.