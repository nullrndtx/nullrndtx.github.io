---
layout: post
title: Change Apache2 Document Root
date: 2016-10-19 15:30:33
---

### Changing apache2 document root

The default document root is set in the 000-default.conf file that is under /etc/apache2/sites-available folder.

```sh
$ cd /etc/apache2/sites-available
$ sudo nano 000-default.conf
```

While the file is opened change DocumentRoot /var/www with your new folder e.g

```
DocumenRoot /home/randalltux/htdocs
```

### Set the right Apache configuration

The configuration of the /var/www folder is under /etc/apache2/apache2.conf. Edit this file to add the configuration of your new document root.

```sh
$ sudo nano /etc/apache2/apache2.conf
```

Copy the following:

```php
<Directory /var/www/>
    Options Indexes FollowSymlinks
    AllowOverride None
    Require all granted
</Directory>
```

and change the directory path

```php
<Directory /home/randalltux/htdocs>
    Options Indexes FollowSymlinks
    AllowOverride None
    Require all granted
</Directory>
```

Restart apache

```sh
$ sudo service apache2 restart
```

Set the right permission

```sh
$ chmod +755 /home/randalltux
$ chmod +755 /home/randalltux/htdocs
```

Now opening http://localhost should work as expected.
