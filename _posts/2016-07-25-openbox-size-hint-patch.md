---
layout: post
title: "Openbox Size Hint Patch"
summary:
---

This is an guide to remove size hints on terminal and forced aspect ratio on mpv/mplayer in OpenBox.

### Step 1 ( clone OpenBox source code )

> git clone https://github.com/danakj/openbox ~/openbox

go to openbox directory

> cd ~/openbox

### Step 2 ( patching )

Edit _openbox/client.c_ file using your favorite editor (i use vim)

> vim openbox/client.c

In this file goto Line 1742 or search for 'PAspect', make the following changes to the file then save and exit

```c
-1742:  if (size.flags & PAspect) {}
+1742:  /*if (size.flags & PAspect) {

-1749:  }
+1749:  }*/

-1760:  if (size.flags & PResizeInc && size.width_inc && size.height_inc)
+1760:  /*if (size.flags & PResizeInc && size.width_inc && size.height_inc)

-1761:     SIZE_SET(self->size_inc, size.width_inc, size.height_inc);
+1761:     SIZE_SET(self->size_inc, size.width_inc, size.height_inc);*/
```

### Step 3 ( compile and install )

Install with the following commands

> ./bootstrap && ./configure --prefix=/usr && make && sudo make install

Wait untill finish, then restart OpenBox or test with another session.
