---
title: Verify Silverlight ComboBox Items
page_title: Verify Silverlight ComboBox Items
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Verifying the items contained in a Silverlight ComboBox DropDownList#

![ComboBox][1]

Verifying the items contained in the DropDownList of a Silverlight ComboBox can be tricky. The first problem you run into is that the items aren't even present in the Silverlight visual tree. Here's what the visual tree of a ComboBox looks like before the drop down is opened:

![NotOpenedComboBox][2]

Notice that there are no drop down items, not even a drop down list. As soon as you open the drop down the items appear in the visual tree:


![OpenedComboBox][3]



Another problem you may run into is that the items placed into the DropDownList can be virtually anything e.g. checkboxes, circles, images and so on, not just text items. In this example we'll assume the web developer put ordinary text blocks in the DropDownList. Verifying other item types is much more difficult and beyond the scope of this article.

The very first step in verifying the drop down items is to simply open the drop down. Your test should look something like this:

![Test][4]

Now that the drop down has been opened we'll be able to get to the ComboBoxItems in the visual tree. Since Test Studio has no built-in verification's of ComboBoxItems we have to resort to code to perform our verification. Let's start by fetching our ComboBox and storing it in a local variable for easy reference:

```C#
ComboBox cbox = Pages.SilverlightApplication3.SilverlightApp.Item0Combobox;
```

Now you may be wondering how did I know to use "Pages.Pale2.SilverlightApp.ComboBoxItem1Combobox"? If you click on the test step that opens the drop down (step 2 in my example) you will see the target element highlighted in Elements Explorer like this:

![Elemenets explorer][5]

By looking at the element hierarchy you can construct the element reference quite easily. You always start with Pages followed by a period. The next part is the name of the page, Pale2 in this case. If there's was a frame involved, that would appear next. Next is the name of the Silverlight application. Most developers leave it at the default of SilverlightApp. Finally comes the element name, ComboBoxItem1Combobox in this case. Put it all together and you get "Pages.Pale2.SilverlightApp.ComboBoxItem1Combobox" in my example. Yours will likely be different. Now that we have a short variable name to reference we can use it in the rest of our code.

The next problem you may run into (depending on the design of the application) is there could be a delay between when the drop down opens and the items appear in the list. Sometimes the application has to communicate with the remote web server to obtain the list of items to be displayed in the drop down. This remote communication can cause a significant delay before the items actually show up. If this is happening in your application, we can synchronize with the items showing up by adding a Wait.For call like this:

```C#
Wait.For<ComboBox>(cb => cb.Items.Count > 0, cbox, 10000);
```

This code will wait up to 10 seconds for the list of available items to be at least 1. The test will fail and abort here if there isn't at least 1 items present after 10 seconds. If you know exactly how many items should show up, you can change "> 0" so something like "== 5" to wait for 5 items to be present. To change the timeout, simply change 10000 to the number of milliseconds you want to use for your timeout.

To verify the number of items presented we use this code:

```C#
IList<ComboBoxItem> items = cbox.Items;

//Log.WriteLine(items.Count + " ComboBoxItem's found");

Assert.AreEqual<int>(5, items.Count);
```

This code will cause the test to fail of the count is something other than 5. Adjust it to match what your ComboBox actually has.

To verify the actual text contain in the drop down we'll need to use code like this:

```C#
//foreach (ComboBoxItem item in items)

//{

//    Log.WriteLine(item.TextBlockContent);

//}

Assert.AreEqual<string>("ComboBoxItem1", items[0].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem2", items[1].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem3", items[2].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem4", items[3].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem5", items[4].TextBlockContent);
```

This code assumes the list of items and their order will never change. The test will immediately fail at the first item that doesn't match. Putting it all together this is our code:


```C#
ComboBox cbox = Pages.Pale2.SilverlightApp.ComboBoxItem1Combobox;

 

IList<ComboBoxItem> items = cbox.Find.AllByType<ComboBoxItem>();

//Log.WriteLine(items.Count + " ComboBoxItem's found");

Assert.AreEqual<int>(5, items.Count);

 

//foreach (ComboBoxItem item in items)

//{

//    Log.WriteLine(item.TextBlockContent);

//}

Assert.AreEqual<string>("ComboBoxItem1", items[0].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem2", items[1].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem3", items[2].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem4", items[3].TextBlockContent);

Assert.AreEqual<string>("ComboBoxItem5", items[4].TextBlockContent);
```

For this code to compile you will need to have two using statements at the top of your code file:

using ArtOfTest.WebAii.Silverlight.UI;
using System.Collections.Generic;

Also be sure your project has references to this DLL:

ArtOfTest.WebAii.dll - contained in the folder C:\Program Files (x86)\Telerik\Test Studio\Bin

> As of release **2017 R3** (v. 2017.3.1010) the default installation path for new installation is **C:\Program Files (x86)\Progress\Test Studio**.

[1]: /img/knowledge-base/verification-kb/verify-silverlight-combobox-items/fig1.png
[2]: /img/knowledge-base/verification-kb/verify-silverlight-combobox-items/fig2.png
[3]: /img/knowledge-base/verification-kb/verify-silverlight-combobox-items/fig3.png
[4]: /img/knowledge-base/verification-kb/verify-silverlight-combobox-items/fig4.png
[5]: /img/knowledge-base/verification-kb/verify-silverlight-combobox-items/fig5.png
