---
title: Coded Steps
page_title: Coded Steps
description: Coded Steps
publish: true
position: 1
slug: ms-coded-steps
previous_url: /test-studio-mobile/getting-started-mb/code-features/coded-steps
---

#Coded Steps

Test Studio Mobile supports coded steps. This allows you to write code and have it executed as a test step. Use a coded step for a scenario that requires more complexity than what can be composed with the [Step Builder]({% slug ms-step-builder%}).

1. Add a Coded Step from the [Step Builder]({% slug ms-step-builder%}).

	![Add Coded step](/img/test-studio-mobile/getting-started-mb/coded-features/coded-steps/fig1.png)

2. Select coding language.

	![Select coding language](/img/test-studio-mobile/getting-started-mb/coded-features/code-behind-file/fig5.png)

	This creates a [code-behind file]({% slug ms-code-behind%}) with an empty test method where you can implement your custom code.

3. In order to execute the code in the test method you should bind it to an existing coded step in the test to which this test class belongs.Double click the coded step in your test in order to access the drop down menu with all valid methods. Select one and save the test.

	> valid methods are methods of a Public Partial Class that inherits *IOSTestBase*, *AndroidTestBase*  or *WebTestBase* depending on the test type you are using.

	![Bind a coded step](/img/test-studio-mobile/getting-started-mb/coded-features/coded-steps/fig3.png)

4. Here is an example how to use a simple "Tap" command and how to access the recorded elements that belong to the particular test.

	> All recorded elements are stored in *Elements* collection.

	```C#
	this.ActiveDevice.IOS.Tap(this.Elements.MyScreen1.UIRoundedRectButton);
	```

	```VB
	Me.ActiveDevice.IOS.Tap(Me.Elements.MyScreen1.UIRoundedRectButton)
	```

See Also
--------

* [Compile Project]({% slug ms-compile-project%})
* [Code Item]({% slug ms-code-item%})
* [Code Behind File]({% slug ms-code-behind%})
* [Android API]({% slug ms-android-api%})
* [iOS API]({% slug ms-ios-api%})
* [Hybrid API]({% slug ms-hybrid-api%})
* [Web API]({% slug ms-web-api%})
