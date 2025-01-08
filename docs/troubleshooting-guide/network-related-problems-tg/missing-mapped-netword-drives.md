---
title: Missing mapped network drives
page_title: Missing mapped network drives
description: "Missing mapped network drives when handling download and upload dialogs in Test Studio test"
position: 1
---
# Missing mapped network drives

## Problem:

When open a new project in Test Studio the browser dialog may not show the mapped network drives:

![missing drives][1]

## Solution:

You need to set the following registry option:

***HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/Windows/CurrentVersion/Policies/System***

    EnableLinkedConnections=1

1.&nbsp; Run **regedit**.

2.&nbsp; Locate *HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/Windows/CurrentVersion/Policies/System*

3.&nbsp; Create a new **DWORD** entry with the name **EnableLinkedConnections** and **value 1**.

![Enable Linked Connections][2]

4.&nbsp; Restart your computer.

5.&nbsp; Now you should be able to see and use the network drives in Test Studio.


[1]: /img/troubleshooting-guide/network-related-problems-tg/fig1.png
[2]: /img/troubleshooting-guide/network-related-problems-tg/fig2.png

