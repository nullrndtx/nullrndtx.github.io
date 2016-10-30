---
layout: post
title: Bash Scripting (Check Root)
summary:
status: draft
hn-discussion:
---

### How to check the bash shell script is being by root or not

Sometimes it is necessary to find out if a shell script is being run as root user or not.
When user account created a user ID is assigned to each user. **BASH** shell stores the user
**ID** in **$UID** variable. Your effective user **ID** is stored in **$EUID** variable.

You can easily add a simple  check at the start or a script

### Using **$ID** Variable

```sh
#!/bin/bash
# Check root user
if [ "$(id -u)" != 0 ]; then
	echo "ERROR! Run this script with root user!"
	exit 1
fi
```

### Using **$EUID** Variable

```sh
#!/bin/bash
# Check root user
if [[ $EUID -ne 0 ]]; then
	echo "ERROR! Run this script with root user!"
	exit 1
fi
```

### Another Way From My Friends

From [https://www.facebook.com/alun.esq165](Fadlun Akbar aka Alunux)

```sh
#!/bin/bash
if [[ "$(whoami)" != "root" ]]; then
	echo "Bukan root"
	exit 1
fi
	echo "root"
```
