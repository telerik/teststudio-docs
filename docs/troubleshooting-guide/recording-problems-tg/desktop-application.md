---
title: Desktop Application
page_title: Desktop Application Will Not Record
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Desktop Application Will Not Record

## PROBLEM


I created a WPF Test and configured my application. When I press **Record**, the application launches but no steps are recorded in Test Studio.


## SOLUTION

Test Studio supports WPF desktop application automation. Test Studio does not support testing against WinForms applications. Ensure the application under test is 100% WPF and contains no non-WPF components.

If you are unsure whether your desktop application is WPF, follow these steps:

1.&nbsp; Open the application you are trying to automate against.

2.&nbsp; Open Test Studio.

3.&nbsp; Create a new WPF test and open it.

4.&nbsp; Click Configure in the Application ribbon.

5.&nbsp; Is the application listed under Active WPF Applications? If not, the application is not compatible.

![Configure][1]

6.&nbsp; Keep in mind that if you manual select the application using the **Browse** button, it will accept any application with an .exe extension. This can lead to a false positive indicated by the green and white check mark. The app will load when you click the Record button, however no steps will record if the application is not WPF. (A recording toolbar may or may not be attached.)

Below is an example of a false positive with the Windows Calculator program. This type of application is not supported by Test Studio.

![Browse][2]

Test Studio will alert you if the selected application is not valid:

![Alert][3]

7.&nbsp; If recording is functioning correctly in most sections of your WPF application but not all, the non-working sections may be designed with non-WPF components. These sections are not supported by Test Studio. An example is a browser control within a WPF app.

> It is not on our road map to implement WinForms support any time soon.

[1]: /img/troubleshooting-guide/recording-problems-tg/desktop-application/fig1.png
[2]: /img/troubleshooting-guide/recording-problems-tg/desktop-application/fig2.png
[3]: /img/troubleshooting-guide/recording-problems-tg/desktop-application/fig3.png
