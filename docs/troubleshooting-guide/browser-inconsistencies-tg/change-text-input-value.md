---
title: Change Text Input Value
page_title: Change Text Input Value
description: "Test Studio Testing Framework "
position: 1
published: false

---
# Change Text Input Value

Given the following element:

	<input type="text">

If its value is changed, Firefox, Chrome, and Safari do not update the DOM and Test Studio's parsed elements do not recognize the changed value. If the input value is retrieved through JavaScript, then all browsers return the correct value.
The correct result is returned if the following code is called for a text input element that has its value modified. This is because the value is retrieved by invoking JavaScript on the browser.

	browser.Find.ByName<HtmlInputText>("oname").Value;

If the code below is used instead, then only the initial value is retrieved. This is because Test Studio uses the parsed DOM elements and the DOM is incorrect.

	string value = browser.Find.ByName("oname").GetAttributeValueOrEmpty("value");

This problem only occurs with text input; it does not appear with button input, for example.