---
layout: post
title: Python Script Check Imap Account
summary:
status: draft
hn-discussion:
---

To check the unread mail count in my IMAP account, i created a little Python sript.
But because i don't want to query the server every second, I'm caching the value in a file
and update it every 30 seconds. Create a cronjob or similiar to update the file.

```python
#!/usr/bin/env python

import imaplib

obj = imaplib.IMAP4_SSL('xxx.xxx.xxx.xxx', '993')
obj.login('user', 'password')
obj.select()
print len(obj.search(None, 'UnSeen')[1][0].split())
```
