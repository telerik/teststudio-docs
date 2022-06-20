---
title: Generate Application Log
page_title: Generate Application Log (Archive)
description: (Archive) Generate application log.
position: 1
---
# How to Generate a Test Studio Application Log #

*I'm experiencing an issue with the Test Studio application (as opposed to an automation challenge). I need to generate an application log file for troubleshooting purposes.*

Test Studio supports logging. The logs are stored in a plain text file in the **"Logs"** folder in the product's installation folder, by default in **"C:\Program Files (x86)\Progress\Test Studio\Logs"**. This feature is initially turned off and you will need to manually turn it on. Please note that this log monitors "application" events. The log will not be of much value in troubleshooting true automation problems (e.g. the test doesn't press the button in my Login page).
 
You might be asked by the Telerik Support team to provide an application log for a particular problem. The best practice here would be to clear the log (if not empty to begin with) and enable it. After this, trigger the problematic behavior and subsequently send the log.


## **Standalone version 2016 R2 Version and Earlier** ##

1.&nbsp; Click the **Help** tab.

2.&nbsp; Click **Enable** in the Logging ribbon.

![Enable log][1]

3.&nbsp; This will turn on logging. After you experience the issue, open the log by clicking the **View Log** button.

![View log][2]

## Run-Time edition ##

### Through Standalone version ###

1.&nbsp; Click **Status** in the **Test tab**.

![Status button][3]

2.&nbsp; Double click on the remote machine that you are interested in:

![Remote machine][4]

3.&nbsp; The remote machine log related controls are placed on the right side of the window as shown on the next screenshot. Press on the **Logging** button to enable it. The **View Log** button will open the current log file at the current state. If click on **Clear Log** button - all previous messages will be deleted.

![View log][9]

### **Standalone version 2017 R1 Version and Earlier** ###

 Click at Logging tab and enable log in. This will turn on logging. After you experience the issue, open the log by clicking the View Log button.

![View log][5]

### Through the registry on the remote machine ###

If you use only Runtime version you will need to manually edit the **Registry** on the machine. Load <a href="http://support2.microsoft.com/kb/136393" target="_blank">Regedit</a> and find the Test Studio folder. The default path is:

* **Computer\HKEY_CURRENT_USER\Software\Wow6432Node\Telerik\Test Studio**

![Registyry][6]

Find (or create) the TraceLogEnabled key in this folder. Double click it and change the Value data to 1. You should also see the TraceLogPath value. This is where the log will be stored. Ensure you include the file name and type:

* **C:\Temp\TraceLog\log.txt**

Find out more about <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log" target="_blank">using the application log</a> in our troubleshooting guide.

[1]: /img/knowledge-base/best-practices-kb/generate-application-log/fig1.png
[2]: /img/knowledge-base/best-practices-kb/generate-application-log/fig2.png
[3]: /img/knowledge-base/best-practices-kb/generate-application-log/fig3.png
[4]: /img/knowledge-base/best-practices-kb/generate-application-log/fig4.png
[5]: /img/knowledge-base/best-practices-kb/generate-application-log/fig5.png
[6]: /img/knowledge-base/best-practices-kb/generate-application-log/fig6.png
[7]: /img/knowledge-base/best-practices-kb/generate-application-log/fig7.png
[8]: /img/knowledge-base/best-practices-kb/generate-application-log/fig8.png
[9]: /img/knowledge-base/best-practices-kb/generate-application-log/fig9.png


