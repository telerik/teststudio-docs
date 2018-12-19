---
title: Error with "Another installation is in progress"
page_title: Error with "Another installation is in progress"
description: "Another installation is in progress"
position: 1
---

#"Another installation is in progress" error

##Problem

While installing Test Studio *Another installation is in progress* appears and it cannot continue:

The installer for Test Studio is a Windows .MSI install file. The above error message appears in case some other install of another .MSI file of either Telerik or some third party product is still in process or never completed properly. 

![Error message][1]

##Solution

You should determine which installation is still in progress and finish it or abort it.

If you're unable to find another install already in progress, you can reboot the computer. This will force any install in process to terminate. Then you can restart the installation of Test Studio.

[1]: /img/troubleshooting-guide/installation-problems-tg/another-installation/fig1.jpg

