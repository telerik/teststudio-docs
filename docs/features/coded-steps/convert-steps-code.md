---
title: Convert All Steps to Code (VS plugin)
page_title: Convert All Steps to Code (VS plugin)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/coded_steps/convert-all-steps-to-code.aspx, /user-guide/coded_steps/convert-all-steps-to-code
position: 6
---
# Convert All Steps to Code (VS plugin)#

The **Generate unit test** button converts your Test Studio test into a unit test. While the original Test Studio test remains intact, changes made to it are not synced to the unit test. Likewise, changes made to the unit test are not synced back to the Test Studio test. A unit test cannot be converted back to a Test Studio test. Since fully coded tests are harder to maintain, we recommend using this feature sparingly and only when absolutely necessary.

![Generate unit test button][1]

The **Unit Test Template Selector** dialog appears and lets you choose a template, i.e. a testing framework. If you have defined some rows of data in the Data Tab, it is converted to XML and placed in a file name you specify for use by the selected testing framework.

![Unit Test Template Selector][2]

A unit test file and XML file containing your data are created in your Test Project.

![Unit Test][3]

**Note:** This conversion is a one-way process. You cannot convert the coded unit test back into a Test Studio test. Also, we do not guarantee the converted test will run perfectly. Sometimes the code needs a little tweaking before it works (e.g. if you have coded steps or dialog handling that does not convert properly).
 
**Note:** When you convert an entire test to code, it doesn't take into account the **Enable Silverlight** setting. You need to enable it in code prior to the LaunchNewBrowser call:

```C#
Manager.Settings.Web.EnableSilverlight = true;
Manager.LaunchNewBrowser();
```

```VB
Manager.Settings.Web.EnableSilverlight = True
Manager.LaunchNewBrowser()
```

[1]: /img/advanced-topics/coded-steps/convert-steps-code/fig1.png
[2]: /img/advanced-topics/coded-steps/convert-steps-code/fig2.png
[3]: /img/advanced-topics/coded-steps/convert-steps-code/fig3.png

