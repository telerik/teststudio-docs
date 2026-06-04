---
title: Missing mapped network drives
page_title: Missing mapped network drives
description: "Missing mapped network drives when handling download and upload dialogs in Test Studio test"
position: 1
---
# Missing mapped network drives

## Problem:

When open a new project in Test Studio the browser dialog may not show the mapped network drives:

![missing drives](/img/troubleshooting-guide/network-related-problems-tg/fig1.png)

## Solution:

You need to set the following registry option:

***HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/Windows/CurrentVersion/Policies/System***

    EnableLinkedConnections=1

1. Run **regedit**.

2. Locate *HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/Windows/CurrentVersion/Policies/System*

3. Create a new **DWORD** entry with the name **EnableLinkedConnections** and **value 1**.

![Enable Linked Connections](/img/troubleshooting-guide/network-related-problems-tg/fig2.png)

4. Restart your computer.

5. Now you should be able to see and use the network drives in Test Studio.



