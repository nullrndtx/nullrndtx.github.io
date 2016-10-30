---
layout: post
title: Fix ZSH Grep Warning
date: 2016-03-18 16:12:54
---

grep-warning:
![alt
text](https://raw.githubusercontent.com/nullrndtx/nullrndtx.github.io/master/_img/grep_error.png "grep-warnning")

### HOW TO FIX?

Copy this grep.zsh lib

```zsh
# is x grep argument available?
grep-flag-available() {
    echo | grep $1 "" >/dev/null 2>&1
}

GREP_OPTIONS=""

# color grep results
if grep-flag-available --color=auto; then
    GREP_OPTIONS+=" --color=auto"
fi

# ignore VCS folders (if the necessary grep flags are available)
VCS_FOLDERS="{.bzr,CVS,.git,.hg,.svn}"

if grep-flag-available --exclude-dir=.cvs; then
    GREP_OPTIONS+=" --exclude-dir=$VCS_FOLDERS"
elif grep-flag-available --exclude=.cvs; then
    GREP_OPTIONS+=" --exclude=$VCS_FOLDERS"
fi

# export grep settings
alias grep="grep $GREP_OPTIONS"

# clean up
unset GREP_OPTIONS
unset VCS_FOLDERS
unfunction grep-flag-available
```

save and close

grep-fix:
![alt
text](https://raw.githubusercontent.com/nullrndtx/nullrndtx.github.io/master/_img/grep_fix.png "grep-fix")
