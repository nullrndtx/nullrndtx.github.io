---
layout: post
title: "Zipping A Directory In Terminal Linux"
date: 2016-07-17 20-39-43 +0700
categories: ['notes']
tags: ['notes']
disqus_identifier: 291267067394962728362982535842105296986
---

How do i zip files in Linux so that i cam email them to my friend? How do i zip files on server using the shell prompt?

Zip is a compression and file packaging utility for Unix, Linux, VMS, MSDOS, OS/2, Windows NT, Minix, Atari, and Machintosh, Amiga and Acron RISC and many other operating systems.

This utility is installed by default on most Linux computers and servers. The program is usefull for packaging a set of files for distribution; for archiving files; and for saving disk space by temporarily compressing unused files or directories

### SYNTAX

Zip's syntax is:

```sh
zip file.zip file1 file2
zip file.zip dir1
zip -option file.zip dir1
```

To zip directory called pics in your home directory (/home/username/pics), type the following command:

```sh
zip -r mypic.zip /home/username/pic
```

or

```sh
zip -r mypic /home/username/pic
```

The -r option recurse into directories (all files and directories inside pics) to produced zip file called mypic.zip. You can travel directory structure recursively starting at the current directory. In this example, all the files matching *.c in the tree starting at the current directory are stored into a zip archive named mywork.zip

```sh
zip -R mywork.zip "*.c"
```

Please not that *.c will match file.c, dir1 /file.c and dir/dir2/.c and so on.
