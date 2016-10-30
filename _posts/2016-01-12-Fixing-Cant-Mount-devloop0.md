---
layout: post
title: Fixing Can't Mount /dev/loop0
comments: True
summary:
status: draft
hn-discussion:
---

I recently ran into this error in which it could not mount /dev/loop0 due to Input Output Error and i just now found a fix and i'am helping everyone that has that error!

### General Error

```
BusyBox vX.XX.X(Ubuntu X:X.X.X-XXXXXX) built-in shell (ash)
Enter 'help' for a list of built-in commands.

(initramfs) mount: mounting /dev/loop0 on //filesystem.squashfs failed: Input/output error
Can not mount /dev/loop0 (/cdrom/casper/filesystem.squashfs) on //filesystem.squashfs
```

This error is really frustrating and after googling for a looong time I still had no fix :(
but then I found out that by not mounting the drives when ubuntu booted up , this can be stopped !
First in the menu that appears , select Default and press Tab.

Change this

> initrd=/ubninit file=/preseed/ubuntu.seed boot=casper quiet splash --
 
to
 
> initrd=/ubninit file=/preseed/custom.seed boot=casper nohd --
