---
title: Generate Unit Test 
page_title: Generate Unit Test | Test Studio Dev Documentation
description: Test Studio Dev allows you to automatically generate a unit test from a recorded test
position: 1
---
# Generate Unit Test from a Recorded Test

The **Generate unit test** button converts your Test Studio Dev test into a unit test. While the original Test Studio test remains intact, changes made to it are not synced to the unit test. Likewise, changes made to the unit test are not synced back to the Test Studio Dev test. A unit test cannot be converted back to a Test Studio Dev test. Since fully coded tests are harder to maintain, we recommend using this feature sparingly and only when absolutely necessary.

![Generate unit test button][1]

The **Unit Test Template Selector** dialog appears and lets you choose a template, i.e. a testing framework. If you have defined some rows of data in the Data Tab, it is converted to XML and placed in a file name you specify for use by the selected testing framework.

![Unit Test Template Selector][2]

A unit test file and XML file containing your data are created in your Test Project.

![Unit Test][3]

>**Note!** This conversion is a one-way process. You cannot convert the coded unit test back into a Test Studio Dev test. Also, we do not guarantee the converted test will run perfectly. Sometimes the code needs a little tweaking before it works (e.g. if you have coded steps or dialog handling that does not convert properly).

**Note:** When you convert an entire test to code, it doesn't take into account the **Enable Silverlight** setting. You need to enable it in code prior to the LaunchNewBrowser call:

```C#
Manager.Settings.Web.EnableSilverlight = true;
Manager.LaunchNewBrowser();
```

```VB
Manager.Settings.Web.EnableSilverlight = True
Manager.LaunchNewBrowser()
```

## Preview Code

Use the **Preview Code** button to see the corresponding code for your Test Studio Dev test as it will look like in a unit test. The code preview can be copied to clipboard to be used in any other program. 

![Preview Code][4]

[1]: images/fig6.png
[2]: images/fig7.png
[3]: images/fig8.png
[4]: images/fig9.png