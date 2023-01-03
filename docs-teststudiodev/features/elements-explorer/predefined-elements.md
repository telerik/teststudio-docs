---
title: Predefined Elements
page_title: Predefined Elements - Test Studio Dev Documentation
description: Test Studio Dev Predefined Elements feature allows you to create tests without having an application UI ready for test. 
position: 2
---
# Predefined Elements

This feature of __Test Studio Dev__ allows you to create your automated tests while the application you will be testing is still in development and does not yet have the UI elements for the test or tests you want to create. You can create your test while waiting for the UI of the application to catch up.

This feature should be extremely helpful for QA engineers since they no longer have to wait until the application feature is developed before creating a test script.

You can start creating your automated tests using predefined elements and add actions or verifications against those elements.

In order to proceed create a Web or WPF test. Navigate to the Elements Explorer of the project:

![Elements explorer VS][16]

Click on Add Element button:

![Add Element][17]

The element gets added in the Predefined Elements section:

![Element Added][18]

Once created you can edit the properties of the element such as ControlType, FriendlyName and Technology type:

![Edit Element's properties][19]

> If you are using Silverlight, please make sure you change the **TechnologyType** to **Silverlight** in order to be able to create the appropriate steps.

You can also use the <a href="/features/recorder/step-builder" target="_blank">Step Builder</a> to create various steps against the element such as actions and verifications:

![Actions/Verifications][20]

* See Also: <a href="/features/elements-explorer/element-mapping" target="_blank">Elements Mapping (IntelliMap)</a>

[16]: images/element-mapping/fig16.png
[17]: images/element-mapping/fig17.png
[18]: images/element-mapping/fig18.png
[19]: images/element-mapping/fig19.png
[20]: images/element-mapping/fig20.png
