---
title: Predefined Elements
page_title: Predefined Elements
description: "Create your automated tests in Test Studio, while the application you will be testing, is still in development and does not yet have its UI elements."
position: 4
---
# Predefined Elements

* [Test Studio Standalone](#test-studio-standalone)
* [Visual Studio Plugin](#visual-studio-plugin)

## Test Studio Standalone

Predefined elements and element mapping is a new Test Studio feature introduced in the R1 2015 release. Now you have the ability to create your automated tests while the application you will be testing is still in development and does not yet have the UI elements for the test or tests you want to create. You can create your test while waiting for the UI of the application to catch up.

This new feature should be extremely helpful for QA engineers since they no longer have to wait until the application feature is developed before creating a test script.

You can start creating your automated tests using predefined elements and add actions or verifications against those elements.  

In order to proceed create a Web or WPF test. Navigate to the Elements tab:

![Elements tab][1]

Click on Add Element button:

![Add Element][2]

The element gets added in the Predefined Elements section:

![Element Added][3]

Once created you can edit the properties of the element such as ControlType, FriendlyName and Technology type:

![Edit Element's properties][4]

> If you are using Silverlight, please make sure you change the **TechnologyType** to **Silverlight** in order to be able to create the appropriate steps.

You can also use the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Builder</a> to create various steps against the element such as actions and verifications:

![Actions/Verifications][5]

## Visual Studio Plugin

In order to proceed create a Web or WPF test. Navigate to the Elements Explorer of the project:

![Elements explorer VS][16]

Click on Add Element button:

![Add Element][17]

The element gets added in the Predefined Elements section:

![Element Added][18]

Once created you can edit the properties of the element such as ControlType, FriendlyName and Technology type:

![Edit Element's properties][19]

> If you are using Silverlight, please make sure you change the **TechnologyType** to **Silverlight** in order to be able to create the appropriate steps.

You can also use the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Builder</a> to create various steps against the element such as actions and verifications:

![Actions/Verifications][20]

<br>
<br>
* See Also: <a href="/features/elements-explorer/element-mapping" target="_blank">Elements Mapping (IntelliMap)</a>


[1]: /img/features/elements-explorer/element-mapping/fig1.png
[2]: /img/features/elements-explorer/element-mapping/fig2.png
[3]: /img/features/elements-explorer/element-mapping/fig3.png
[4]: /img/features/elements-explorer/element-mapping/fig4.png
[5]: /img/features/elements-explorer/element-mapping/fig5.png

[16]: /img/features/elements-explorer/element-mapping/fig16.png
[17]: /img/features/elements-explorer/element-mapping/fig17.png
[18]: /img/features/elements-explorer/element-mapping/fig18.png
[19]: /img/features/elements-explorer/element-mapping/fig19.png
[20]: /img/features/elements-explorer/element-mapping/fig20.png
