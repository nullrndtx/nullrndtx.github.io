---
layout: post
title: PHP Directory Listing
summary:
status: draft
hn-discussion:
---

Many times we have to display the list of files in a directory. We can keep the
script in any location and by using the file path we can display the files
inside in the directory. Read the path and the script will take care to list
the files inside that. Here is the code:

```php
// open the current directory by opendir
$handle=opendir(".");

while (($file = readdir($handle))!==false) {
  echo "$file <br>";
}

closedir($handle
```

### Reading and displaying all images present inside a directory

We can use the same code to read all the files in a directory and all the files
in a directory and assuming that all are images, we can display them. Here is
the code:

```php
$path='images/'; // change the path here related to this page
$handle=opendir($path);

while (($file = readdir($handle))!==false) {
  if(strlen($file)>3){echo "<img src=$path$file> <br>";}
}

closedir($handle);
```

You can also list the files and directories by using
[http://www.plus2net.com/php_tutorial/scandir.php](dir function scandir())
