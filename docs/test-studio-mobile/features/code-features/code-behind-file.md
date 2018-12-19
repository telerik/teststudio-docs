---
title: Code-Behind File
page_title: Code-Behind File
description: Code-Behind File
publish: true
position: 2
slug: ms-code-behind
previous_url: /test-studio-mobile/getting-started-mb/code-features/code-behind-file
---
#Code-Behind File

You can create a code behind file for each test where you can implement [coded steps]({% slug ms-coded-steps%}) and custom test classes.

There are two methods of creating a coded behind file for your test:

1. Add a Coded Step from the [Step Builder]({% slug ms-step-builder%}).

	![Add Coded step](/img/test-studio-mobile/getting-started-mb/coded-features/coded-steps/fig1.png)

2. Right click the test and select **Add Code-Behind**.

	![Add Coded Behind](/img/test-studio-mobile/getting-started-mb/coded-features/coded-steps/fig2.png)

	Select coding language.

	![Select coding language](/img/test-studio-mobile/getting-started-mb/coded-features/code-behind-file/fig5.png)

Both actions create a code-behind file with an empty test method where you can implement your custom code. Each code behind file can contain multiple test methods. 

See [Coded Steps]({% slug ms-coded-steps%}) article which describes how to execute the code in the test method.

You can also implement multiple test classes in a single code behind file. If methods of the test class will be bound to coded steps the class must  inherit *IOSTestBase*, *AndroidTestBase* or *WebTestBase* class depending on the type test you are using as shown below. 

![Class code](/img/test-studio-mobile/getting-started-mb/coded-features/code-behind-file/fig3.png)


In order to use the methods from a particular class you should bind the test to that class. You can do this from the test's properties, select the test from the [Project Explorer]({% slug ms-project-explorer%}) so its properties are shown in the Properties pane.

![Class map](/img/test-studio-mobile/getting-started-mb/coded-features/code-behind-file/fig4.png)


See Also
--------

* [Compile Project]({% slug ms-compile-project%})
* [Code Item]({% slug ms-code-item%})
* [Coded Steps]({% slug ms-coded-steps%})
* [Android API]({% slug ms-android-api%})
* [iOS API]({% slug ms-ios-api%})
* [Hybrid API]({% slug ms-hybrid-api%})
* [Web API]({% slug ms-web-api%})
* [Base Test Methods]({% slug ms-basetest-methods%})