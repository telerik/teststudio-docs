---
title: Check Javascript Errors
page_title: Check Javascript Errors
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 4
---
# Check for JavaScript Errors #

Telerik Testing Framework allows you to verify if there are any JavaScript errors on the currently loaded page. The below example demonstrates how to collect the errors in a list and a possible approach how to use these. The sample code will fail the test if there are errors on the page.

> The page in the current example does not actually contain JavaScript errors. Therefore these are invoked on purpose to demonstrate the feature.

#### __[C#]__

    {{region }}

    // Navigate to a page
    Manager.ActiveBrowser.NavigateTo("https://www.google.com");
            
    // Invoke JS errors
    Manager.ActiveBrowser.Actions.InvokeScript("window.console.error('test test')"); 
    Manager.ActiveBrowser.Actions.InvokeScript("window.console.error('test test')"); 
    Manager.ActiveBrowser.Actions.InvokeScript("window.console.error('test test')"); 
    Manager.ActiveBrowser.Actions.InvokeScript("window.console.error('test error')"); 
            
    // Collect the JS errors (if any) in a collection          
    List<ArtOfTest.WebAii.Javascript.JavascriptConsoleError> currentErrorsOnPage = ActiveBrowser.Actions.CheckConsoleForJsErrors();
            
    // Check if there are JS errors in the browser console and log these
    if (currentErrorsOnPage.Count() == 0)
        {
            Log.WriteLine("There are no JavaScript errors!"); 
        }
        else
        {
            // Log the number of error types detected on the current page 
            Log.WriteLine("There are " + currentErrorsOnPage.Count().ToString() + " types of JS errors on current page.");
                
            // Itearete each error type and log its text and count
            foreach (ArtOfTest.WebAii.Javascript.JavascriptConsoleError err in currentErrorsOnPage)
                {
                    Log.WriteLine("The count of errors on page with content " + err.ErrorContent.ToString() + " is " + err.NumberOfOccurences.ToString()); 
                }
            }
            
    // Assert if there are any errors on the current page
    Assert.AreEqual(0, currentErrorsOnPage.Count());
    {{endregion}}

> __Note:__ The JS error check step detects only JavaScript errors. Any errors related to not loaded resources will not be detected. An example for such console error is listed below:<br>
<br>
> _Failed to load resource: the server responded with a status of 404 (Not Found)_