---
title: Code Item
page_title: Code Item
description: Code Item
publish: true
position: 3
slug: ms-code-item
previous_url: /test-studio-mobile/getting-started-mb/code-features/code-item,/test-studio-mobile/getting-started-mb/code-features
---
#Code Item

Add a code item to create a utility class that defines a set of methods which perform common, often re-used functions. The code item can be used also as a helper class which can assist in providing some extended functionality for your test project.

##How To Create Code Item

1. Right click on the project in the [Project Explorer]({% slug ms-project-explorer%}) or on a folder in the project and click **Add Code Item**.

	![Add Code Item](/img/test-studio-mobile/getting-started-mb/coded-features/code-item/fig1.png)

2. Choose the coding language.

	![Choose coding language](/img/test-studio-mobile/getting-started-mb/coded-features/code-item/fig7.png)

3. Choose a name and and click **OK** (HelperClass in our example). 

	![Name of the coded item](/img/test-studio-mobile/getting-started-mb/coded-features/code-item/fig2.png)

4. The Code Item with HelperClass name is created under the selected location.

	![Created code item](/img/test-studio-mobile/getting-started-mb/coded-features/code-item/fig3.png)

##How To Use Code Item

This is an example how to use the code item.

1. Open the already created coded item (*HelperClass*).

2. Create a simple [Query]({% slug ms-create-query%}) which locates an element with class *UIStepper* and *Index* 1.

	```C#
	public static IOSQuery UIStepperControl = new IOSQuery() { Class = "UIStepper", Index = 1};
	```

	```VB
	Public Shared UIStepperControl As New IOSQuery() With {.Class = "UIStepper", .Index  = True}
	``` 

	![Create a query](/img/test-studio-mobile/getting-started-mb/coded-features/code-item/fig4.png)

3. In order to access the functions and methods from the Code Item in the test code-behind file you should add an using statement which matches the **namespace** of the **HelperClass**.

	![Using statement](/img/test-studio-mobile/getting-started-mb/coded-features/code-item/fig5.png)


See Also
--------

* [Compile Project]({% slug ms-compile-project%})
* [Code-Behind File]({% slug ms-code-behind%})
* [Coded Steps]({% slug ms-coded-steps%})
* [Android API]({% slug ms-android-api%})
* [iOS API]({% slug ms-ios-api%})
* [Hybrid API]({% slug ms-hybrid-api%})
* [Web API]({% slug ms-web-api%})
* [Base Test Methods]({% slug ms-basetest-methods%})