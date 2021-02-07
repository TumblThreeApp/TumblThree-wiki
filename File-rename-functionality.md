## Specify a template for how the files shall be named:

In the settings a filename template can be specified. This setting is taken over to every newly added blog. Inside the blog's settings it can be adapted individually.

The following tokens can be used in the filename template and are replaced:
```
  %f  original filename (default)
  %d  post date (yyyyMMddHHmmss)
  %u  post timestamp (number)
  %p  post title (shorted if needed…)
  %i  post id
  %n  image index (of photo sets)
  %t  for all tags (cute+cats,big+dogs)
  %r  for reblog ("" / "reblog")
  %s  slug (last part of a post's url)
  %k  reblog-key
Mandatory tokens (if not using token %f) to make filenames unique:
  %x  "_{number}" ({number}: 2..n) appended to filename
  %y  " ({number})" ({number}: 2..n) appended to filename
```
Lower and upper case letters can be used to specify a token.

Be aware that the filename template should contain a uniqueness. Where as %f is the most unique resp. the old file naming style. But a combination out of `%d`, `%u`, `%i` or `%k` plus `%n` is also good. For that reason the template must end with either `%x` or `%y`, except when the old file naming style is used.

An empty field will be automatically reverted to the default template of `%f` which is the old file naming style.

With the option "group photo sets" enabled the following applies additionally:
  If the image belongs to a photo set and
  * `%i` is specified: `%i` will be replaced with post id and image index ("{post id}\_{image index}")
  * `%i` is not given: the filename will be "{post id}\_{image index}\_{rest of the template}"

If the image index token (`%n`) is used, but the media isn't part of a photo set, then the token is ignored and a character repetition is removed (eg. `%i_%n_%f` -> `%i_%f`) in the generated filename.

The post title (`%p`) will be automatically shorted if the total path length would be too long.

Note: Windows 10 version 1607 and later can be configured to remove the maximum path length limitation of 260 characters.
