---
layout: post
title: Youtube-dl Installer Written In Python
comments: True
summary:
status: draft
hn-discussion:
---

```python
#!usr/local/bin/python3

import os
import urllib.request
import getpass


print("bienvenid@ / welcolme " + getpass.getuser())


def youtube():
    print("""
Y88b   d88P                   888             888                           888 888 
 Y88b d88P                    888             888                           888 888 
  Y88o88P                     888             888                           888 888 
   Y888P     .d88b.  888  888 888888 888  888 88888b.   .d88b.          .d88888 888 
    888     d88""88b 888  888 888    888  888 888 "88b d8P  Y8b        d88" 888 888 
    888     888  888 888  888 888    888  888 888  888 88888888 888888 888  888 888 
    888     Y88..88P Y88b 888 Y88b.  Y88b 888 888 d88P Y8b.            Y88b 888 888 
    888      "Y88P"   "Y88888  "Y888  "Y88888 88888P"   "Y8888          "Y88888 888
    
    
    by:https://www.facebook.com/archdesktop""")


    dir = os.chdir("/usr/local/bin/")
    descarga = urllib.request.urlretrieve("https://yt-dl.org/latest/youtube-dl","youtube-dl")
    permisos = os.system("sudo chmod a+x /usr/local/bin/youtube-dl")


    print ("""
______  _         _       _     
|  ___|(_)       (_)     | |    
| |_    _  _ __   _  ___ | |__  
|  _|  | || '_ \ | |/ __|| '_ \ 
| |    | || | | || |\__ \| | | |
\_|    |_||_| |_||_||___/|_| |_|""")

    limpiar = os.system("clear")

    print ("""

  ,ad8888ba,                                      88      88                                    
 d8"'    `"8b                                     88      88                                    
d8'                                               88      88                                    
88              ,adPPYba,    ,adPPYba,    ,adPPYb,88      88,dPPYba,   8b       d8   ,adPPYba,  
88      88888  a8"     "8a  a8"     "8a  a8"    `Y88      88P'    "8a  `8b     d8'  a8P_____88  
Y8,        88  8b       d8  8b       d8  8b       88      88       d8   `8b   d8'   8PP"""""""  
 Y8a.    .a88  "8a,   ,a8"  "8a,   ,a8"  "8a,   ,d88      88b,   ,a8"    `8b,d8'    "8b,   ,aa  
  `"Y88888P"    `"YbbdP"'    `"YbbdP"'    `"8bbdP"Y8      8Y"Ybbd8"'       Y88'      `"Ybbd8"'  
                                                                           d8'                  
                                                                          d8'                 """)
                                
if getpass.getuser() =="root":
    youtube()

else:
    print("""please,you run script : sudo su ; python3 youtube_dl.py




 
                     ***                  ***
                    *****                *****
                    *****                *****
                     ***                  ***
          ***                                        ***
           ***                                      ***
            ***                                    ***
             ***                                  ***
               ***                              ***
                 ***                          ***
                   ***                      ***
                      **********************
                         ****************
""") 
```

This script is written by Jonaypython you can see on his [Github](https://github.com/jonaypython)