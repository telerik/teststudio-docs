---
title: Invoke Blind Keyboard Typing
page_title: Invoke Blind (Element Independent) Keyboard Typing
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Invoke "Blind" (Element Independent) Keyboard Typing

## PROBLEM

You need to type text and/or characters into an element. A "normal" Test Studio Type step is a complex action. The element that needs to be typed into has to be located first. The typing itself works directly on the DOM. There are some situations where you will need to invoke true simulated desktop typing (identical to the physical action of typing text or pressing a character on the keyboard). This type of typing disregards the element it is typing into (hence the term "blind"). This is often used as a temporary solution to an automation problem. 

## SOLUTION

Start the Test Studio recorder and navigate to your application. Go to the page in your application that holds the element that needs to be typed into. First you need to record an action that will bring browser's focus to that element. Typically this is a mouse click. However, Test Studio doesn't record clicks on some types of elements (e.g. HTML Input field). Because of this you might need to use alternatives like recording "Tab" button press in order to get the browser's focus on the desired element. Now any "blind" typing we implement in the next step will get typed into this element. 

The "blind" typing actions itself could be implemented in a <a href="/features/custom-steps/script-step" target="_blank">Coded Step</a>.

Here's a line of sample code that types "*This is a sample*":

```C#
    Manager.Desktop.KeyBoard.TypeText("This is a sample", 200);
```
```VB
    Manager.Desktop.KeyBoard.TypeText("This is a sample", 200)
```

Here's a line of sample code that presses the ENTER key: 

```C#
    Manager.Desktop.KeyBoard.KeyPress(Keys.Enter, 200);
```
```VB
    Manager.Desktop.KeyBoard.KeyPress(Keys.Enter, 200)
```


**Manager.Desktop.KeyBoard** contains many additional methods you might also find useful:

![Additional Methods][1]

[1]: /img/troubleshooting-guide/test-execution-problems-tg/invoke-blind-keyboard-typing/fig1.png

>To be able to use the code above the assembly **System.Windows.Forms.dll** needs to be <a href="/features/coded-steps/add-assembly-reference" target="_blank">referenced</a> in the Project settings.<br>