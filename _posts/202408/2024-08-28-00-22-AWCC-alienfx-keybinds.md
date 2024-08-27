---
title: Dell AWCC alienfx keybinds, Media Control
date: 2024-08-28 00:22:00+0800
categories: ["Software"]
tags: ["AWCC"]
author: <admin> 
---

Install [AutoHotKey](https://www.autohotkey.com/). 

My AHK version is 2.0.*.

Different versions have differences in code syntax.

To `play next song`, create a new `.ahk` script,
```
Send("{Media_Next}")
```

Save the file.

Open AWCC, in the `shortcut` tab,

![alt text](/assets/img/posts/awcc%20keybinds.png)

Clikc `BROWSE` and choose the `.ahk` file you just created.

Similarly, to `play previous song`, the script is
```
Send("{Media_Prev}")
```

To `play and pause`, the script is
```
Send("{Media_Play_Pause}")
```
