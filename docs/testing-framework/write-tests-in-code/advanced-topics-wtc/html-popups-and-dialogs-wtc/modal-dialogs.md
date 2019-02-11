---
title: Modal Dialogs
page_title: Modal Dialogs
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 2
---
#Handling IE Modal Dialogs#

![Modal Dialog][1]

The main difference between IE modal dialogs and the HTML Pop-ups is that the modal dialog stays in focus even when you try to focus back on the parent window, while the HTML pop-up is just like any other browser instances.
 
IE modal dialogs require special handling. They don't act like standard HTML pop-up windows, which means the standard approach does not work. Here is an example of how to code for the IE modal dialog special case:

```C#
[TestMethod]
[Description("How to access and handle IE's modal dialogs")]
public void IEModalDialogsSupport()
{
     Manager.LaunchNewBrowser(BrowserType.InternetExplorer, true);
     ActiveBrowser.NavigateTo(TESTPAGE2);
  
     // Open the popup using mouse click so it doesn't hang execution.
     Find.ByAttributes<HtmlInputButton>("type=button").MouseClick();
  
    // ** Special IE Code. Given that IE Modal Dialog is an IE specific feature.
    if (ActiveBrowser.BrowserType == BrowserType.InternetExplorer)
     {
         ArtOfTest.WebAii.BrowserSpecialized.InternetExplorer.InternetExplorerActions ieActions = (ArtOfTest.WebAii.BrowserSpecialized.InternetExplorer.InternetExplorerActions)ActiveBrowser.Actions;
  
         // Connect the dialog
         ieActions.ConnectIEDialog("Modal1 -- Webpage Dialog", 300);
         Manager.WaitForNewBrowserConnect("dialog.html", true, 10000);
         Assert.IsTrue(ActiveBrowser.IsIEDialog);
  
         // The ActiveBrowser instance is now the dialog instance. Do what ever you want with the dialog
         ActiveBrowser.Find.ByTagIndex<HtmlContainerControl>("H1", 0).BaseElement.SetValue<string>("style.backgroundColor", "red");
  
         // Once done, make sure to close the dialog. 
         // Even if the dialog is closed due to a button click within the dialog, you still need this line
         // at this point to revert the ActiveBrowser instance to the main instance. We are searching for a
         // good approach to make this automatic.
         ActiveBrowser.Close();
     }
    Assert.IsFalse(ActiveBrowser.IsIEDialog);
  
    // The ActiveBrowser is back to the main browser window.
     ActiveBrowser.NavigateTo("http://www.google.com");
}
```
```VB
<TestMethod(), _
Description("How to access and handle IE's modal dialogs")> _
Public Sub IEModalDialogsSupport()
  
     Manager.LaunchNewBrowser(BrowserType.InternetExplorer, True)
     ActiveBrowser.NavigateTo(TESTPAGE2)
  
     ' Open the popup using mouse click so it doesn't hang execution.
     Find.ByAttributes(Of HtmlInputButton)("type=button").MouseClick()
  
     ' ** Special IE Code. Given that IE Modal Dialog is an IE specific feature.
     If (ActiveBrowser.BrowserType = BrowserType.InternetExplorer) Then
  
        Dim ieActions As ArtOfTest.WebAii.BrowserSpecialized.InternetExplorer.InternetExplorerActions = CType(ActiveBrowser.Actions, ArtOfTest.WebAii.BrowserSpecialized.InternetExplorer.InternetExplorerActions)
  
         ' Connect the dialog
          ieActions.ConnectIEDialog("Modal1 -- Webpage Dialog", 300)
          Manager.WaitForNewBrowserConnect("dialog.html", True, 10000)
  
          Assert.IsTrue(ActiveBrowser.IsIEDialog)
  
         ' The ActiveBrowser instance is now the dialog instance. Do what ever you want with the dialog
          ActiveBrowser.Find.ByTagIndex(Of HtmlContainerControl)("H1", 0).BaseElement.SetValue(Of String)("style.backgroundColor", "red")
  
         ' Once done, make sure to close the dialog. 
         ' Even if the dialog is closed due to a button click within the dialog, you still need this line
         ' at this point to revert the ActiveBrowser instance to the main instance. We are searching for a
         ' good approach to make this automatic.
          ActiveBrowser.Close()
  
     End If
  
     Assert.IsFalse(ActiveBrowser.IsIEDialog)
  
     ' The ActiveBrowser is back to the main browser window.
     ActiveBrowser.NavigateTo("http://www.google.com")
  
End Sub
```

[1]: /img/testing-framework/write-tests-in-code/advanced-topics-wtc/html-popups-and-dialogs-wtc/modal-dialogs/fig1.png


