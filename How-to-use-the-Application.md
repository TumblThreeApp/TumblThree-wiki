## Application Usage:

* Extract the .zip file and run the application by double clicking TumblThree.exe.
* Copy the url of any tumblr.com blog you want to backup from into the textbox at the bottom left. Afterwards, click on 'Add Blog' on the right side of it.
* Alternatively, if you copy (ctrl-c) a whole _tumblr.com_ blog url from the address bar/a text file, the clipboard monitor from TumblThree will detect it and automatically add the blog.
* To start the download process, click on 'Crawl'. The application will regularly check for (new) blogs in the queue and start processing them, until you stop the application by pressing 'Stop'. So, you can either add blogs to the queue via 'Add to Queue' or double click first and then click 'Crawl', or you start the download process first and add blogs to the queue afterwards.
* A light blue bar left to the blog in the queue indicates a actively downloading blog.
* The blog manager on the left side also indicates the state of each blog. A red background shows an offline blog, a green background an actively crawling blog and a purple background an enqueued blog.
* You change the download location, the number of concurrent connections, the default backup settings for each newly added blog and various other settings in the 'Settings'. 
* In the Details window you can view statistics of your blog and set blog specific options. You can choose here what type of posts (photo, video, audio, text, conversation, quote, link) to download.
* For downloading only tagged posts, you'll have to do some steps:
  1. Add the blog url.
  2. Open the blog in the details tab, enter the tags in the Tags textbox in a comma separated list without the leading hash (#) sign. E.g. _great big car,bears_ would search for images that are tagged for either a _great big car_ or _bears_ or both.
* For downloading password protected blogs, you'll have to do some steps:
  1. Add the blog url.
  2. Open the blog in the details tab, enter the password in the Password textbox.
* For downloading hidden blogs (login required blogs), you have to do some steps:
  1. Go to Settings, click the Authenticate button. Logon to tumblr using an account. After successful logon you can close the window. The cookies are cached and normally you don't need to repeat this for a while.
  2. Add the blog url.
* For downloading liked photos and videos, you'll have to do some steps:
  1. Go to Settings, click the Authenticate button. Logon to tumblr using an account. After successful logon you can close the window. The cookies are cached and normally you don't need to repeat this for a while.
  2. Add the blog url including the liked/by string in the url (e.g. https://www.tumblr.com/liked/by/wallpaperfx/).
  3. For downloading your own likes, make sure you've (temporarily) enabled the following options in your blogs settings (i.e. https://www.tumblr.com/settings/blog/yourblogname):
      * Likes -> Share posts you like (to enable the publicly visible liked/by page)
      * Visibility -> _blog_ is explicit (to see/download NSFW likes)
* For downloading photos and videos from the tumblr search, you'll have to do some steps:
  1. Add the search url including your key words separated by plus signs (+) in the url (e.g. https://www.tumblr.com/search/my+special+tags).
* For downloading photos and videos from the tumblr tag search, you'll have to do some steps:
  1. Go to Settings, click the Authenticate button. Logon to tumblr using an account. After successful logon you can close the window. The cookies are cached and normally you don't need to repeat this for a while.
  2. Add the search url including your tags separated by plus signs (+) in the url (e.g. https://www.tumblr.com/tagged/my+special+tags).
* Key Mappings:
  * double click on a blog adds it to the queue
  * drag and drop of blogs from the manager (left side) to the queue.
  * space -- start crawl
  * ctrl-space -- pause crawl
  * shift-space -- stop crawl
  * del -- remove blog from queuelist
  * shift-del -- remove blog from blogmanager.
  * ctrl-shift-g -- manually trigger the garbage collection