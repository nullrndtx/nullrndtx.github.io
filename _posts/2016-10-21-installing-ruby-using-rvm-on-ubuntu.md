---
layout: post
title: "Installing Ruby Using rvm On Ubuntu"
summary:
---

Run the following command:

```sh
curl -L https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
echo "source ~/.rvm/scripts/rvm" >> ~/.bashrc or echo "source ~/.rvm/scripts/rvm" >> ~/.zshrc
source ~/.bashrc or source ~/.zshrc
rvm install 2.3.1
rvm use 2.3.1 --default
```

> ruby 2.3.1p112 (2016-04-26 revision 54768) [x86_64-linux]
