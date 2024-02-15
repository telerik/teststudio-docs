---
title: Minimized RDC
page_title: Minimized RDC
description: Scheduled tests cannot be run on minimized RDC. To run tests on a remote machine while the RDC window is minimized, add registry keys on the computer from which you connect to the remote machine
position: 1
---
#Minimized Remote Desktop Connection#

*I am executing tests on a remote machine using Remote Desktop Connection/Protocol. It works correctly as long as the RDC window is active and/or maximized. However the tests fail when the RDC window is minimized.*

##Solution##

This is a common issue with all UI automation tools. To run tests on a remote machine while the RDC window is minimized, add registry keys on the computer from which you connect to the remote machine:

1.&nbsp; Click the Windows Start button.

2.&nbsp; Type *regedit* in the Run box and press Enter.

**For 32-bit Windows**

1.&nbsp; Find the registry key:

* **HKEY_LOCAL_MACHINE\Software\Microsoft\Terminal Server Client**

2.&nbsp; Create a DWORD value with the name *RemoteDesktop_SuppressWhenMinimized* and set its value to 2.

**For 64-bit Windows**

1.&nbsp; Find the registry keys:

* **HKEY_LOCAL_MACHINE\Software\Microsoft\Terminal Server Client**

* **HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Terminal Server Client**

2.&nbsp; Create a DWORD value with the name *RemoteDesktop_SuppressWhenMinimized* and set its value to 2.

> **Note** In specific configurations, a policy or a setting which force HKEY_CURRENT_USER to override the HKEY_LOCAL_MACHINE, you might have to modify the above registry keys under **HKEY_CURRENT_USER** instead.