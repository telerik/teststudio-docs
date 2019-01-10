---
title: Wait for Element in Code
page_title: Wait for Element in Code
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/general/wait-for-element-to-exist-in-code.aspx, /user-guide/code-samples/general/wait-for-element-to-exist-in-code
position: 1
---
#Wait for Element in Code#

*In a coded step you need to wait for an element to exist before performing an action or a verification against that element. Perhaps you selected to "Customize Step in Code" and the default element wait time is not sufficient.*

##Solution##

After customizing a step in code you may have code that looks like this for an HTML element:

```C#
//Check 'VehicleCheckBox0' to be 'False'
Pages.HTMLFormsAndInput.VehicleCheckBox0.Check(true, true);
```


Or like this for a Silverlight or WPF element:


```C#
//LeftClick on CheckBoxCheckbox
Pages.Pale2.SilverlightApp.CheckBoxCheckbox.Click(ArtOfTest.WebAii.Core.MouseClickType.LeftClick, true, true, 8, 7, ArtOfTest.Common.OffsetReference.TopLeftCorner, ArtOfTest.Common.ActionPointUnitType.Pixel, ((System.Windows.Forms.Keys)(0)));
```


In the above code sample, the parts **Pages.HTMLFormsAndInput.VehicleCheckBox0 and Pages.Pale2.SilverlightApp.CheckBoxCheckbox** actually perform an implied Find under the hood. This implied Find uses the global timeout setting of 10 seconds by default. If the element does not exist within this 10 seconds, your test fails indicating an "element not found" error.
 
You might think you could avoid this by calling the **Wait.ForExists** function on the element like this:

```C#
Pages.HTMLFormsAndInput.VehicleCheckBox0.Wait.ForExists(30000);
```


However, **Pages.HTMLFormsAndInput.VehicleCheckBox0** performs the implied Find using the global timeout setting prior to calling the **Wait.ForExists function**. 
Instead, for HTML elements, you should precede your line of code with an **ActiveBrowser.WaitForElement** call that uses the Find Expression for the element you need to wait for:

```C#
ActiveBrowser.WaitForElement(Pages.HTMLFormsAndInput.Expressions.VehicleCheckBox0, 33000, false);
 
//Check 'VehicleCheckBox0' to be 'False'
Pages.HTMLFormsAndInput.VehicleCheckBox0.Check(true, true);
```

In this sample, **Pages.HTMLFormsAndInput.Expressions.VehicleCheckBox0** returns the Find Expression associated with the **VehicleCheckBox0** element, then calls **WaitForElement** with a 33 second timeout parameter. This will have the desired effect of waiting 33 seconds for the element to exist prior to acting on it.
 
For **Silverlight** elements, precede your line of code with something like this:

```C#
CheckBox cbox = Pages.SilverlightGridControl.SilverlightApp.Get<CheckBox>(Pages.SilverlightGridControl.SilverlightApp.Expressions.Item0Checkbox, true, 33000);
 
//LeftClick on CheckBoxCheckbox
Pages.Pale2.SilverlightApp.CheckBoxCheckbox.Click(ArtOfTest.WebAii.Core.MouseClickType.LeftClick, true, true, 8, 7, ArtOfTest.Common.OffsetReference.TopLeftCorner, ArtOfTest.Common.ActionPointUnitType.Pixel, ((System.Windows.Forms.Keys)(0)));
```


In this sample, **Pages.SilverlightGridControl.SilverlightApp.Expressions.Item0Checkbox** returns the Find Expression associated with the Item0Checkbox element. The Find Expression is used in the Get method with a 33 second timeout parameter to wait for the element to exist and return it as an object. This will have the desired effect of waiting 33 seconds for the element to exist prior to acting on it.





