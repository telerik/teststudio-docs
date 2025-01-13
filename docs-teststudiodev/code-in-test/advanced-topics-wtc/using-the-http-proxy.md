---
title: Using the HTTP Proxy
page_title: Using the HTTP Proxy
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Using the HTTP Proxy

Telerik Testing framework includes the ArtOfTest.WebAii.Messaging.Http namespace. With it you have the ability to intercept raw HTTP traffic under the cover. Using the HTTP proxy you can intercept an HTTP request originating from the browser before it is sent to the web server and/or intercept HTTP responses coming from the web server just before they reach the browser and are rendered by it. This functionality opens up the framework to be used in a wider range of automation scenarios like:

* **Security Testing**: In your listener you have access to all the basic HTTP Request/Response properties and you can examine, inject, alter or do whatever you want with them.

* **Performance Testing**: You can use the HTTP listeners to look at file sizes you are sending or receiving and even build regression unit tests that make sure your files don't grow beyond a certain size.

* **Page Synchronization**: You can now sync your test to specific requests and have the ability to detect Ajax requests over the wire. We plan to add more extended object modeling for this.
 
In this namespace you will find the following methods classes:

<table class="docs">
<tr>
	<th>Class</th><th>Description</th>
</tr>
<tr>
	<td>**HttpProxyManager**</td>
	<td>Manages the HTTP proxy agent.</td>
</tr>
<tr>
	<td>**HttpRequest**</td>
	<td>Used to create and manipulate an HTTP request.</td>
</tr>
<tr>
	<td>**HttpRequestEventArgs**</td>
	<td>EventArgs subclass that wraps an HTTP request, and possibly the related response.</td>
</tr>
<tr>
	<td>**HttpResponse**</td>
	<td>Class wrapper of an HTTP response.</td>
</tr>
<tr>
	<td>**HttpResponseEventArgs**</td>
	<td>EventArgs subclass that wraps an HTTP response and the related request.</td>
</tr>
<tr>
	<td>**RequestListenerInfo**</td>
	<td>Wraps a listener for BeforeRequest events from the proxy.</td>
</tr>
<tr>
	<td>**ResponseListenerInfo**</td>
	<td>Wraps a listener for BeforeResponse events from the proxy.</td>
</tr>
<table>

You must enable the HTTP proxy before you can start using it. This setting is turned off by default. This can be done either by adding the setting to your .config file or modifying the setting in the Settings object. To add the setting to your .config file add this to your .config file:


````XML
<WebAii.Settings
    Manager.Settings.Web.UseHttpProxy="true"
/>
````

To enable this setting in the Settings object, add code to your initialization section like this:

````C#
// This will get a new Settings object. If a configuration
// section exists, then settings from that section will be
// loaded
Settings settings = GetSettings();
 
// Override the settings you want. For example:
settings.Web.UseHttpProxy = true;
 
// Now call Initialize again with your updated settings object
Initialize(settings, new TestContextWriteLine(this.TestContext.WriteLine));
````
 

````VB
' This will get a new Settings object. If a configuration
' section exists, then settings from that section will be
' loaded
Dim settings As Settings = GetSettings()
 
' Override the settings you want. For example:
settings.UseHttpProxy = True
 
' Now call Initialize again with your updated settings object
Initialize(settings, New TestContextWriteLine(AddressOf Me.TestContext.WriteLine))
````
Now that we have the HTTP proxy turned on we can start using it. Here's an example of how we would detect that a response coming back from the web server is an image response.

````C#
[TestMethod]
public void ImageDetection()
{
    // Launch a new browser window
    Manager.LaunchNewBrowser(BrowserType.InternetExplorer);
 
    // Add our HTTP response event handler
    ResponseListenerInfo li = new ResponseListenerInfo(CheckTypeForImage);
    Manager.Http.AddBeforeResponseListener(li);
 
    // Navigate to a website containing images
    ActiveBrowser.NavigateTo("http://news.google.com/");
 
    // We don't need the event handler any longer
    Manager.Http.RemoveBeforeResponseListener(li);
}
 
private void CheckTypeForImage(object sender, HttpResponseEventArgs e)
{
    Log.WriteLine(String.Format("Request for {0}", e.Response.Request.RequestUri));
    if (e.Response.IsImage)
    {
        Log.WriteLine(String.Format("Image detected; MIME type: {0}",
            e.Response.Headers["Content-Type"]));
    }
    else
    {
        Log.WriteLine(String.Format("Not an image; MIME type: {0}",
            e.Response.Headers["Content-Type"]));
    }
}
````
 

````VB
<TestMethod()> _
Public Sub ImageDetection()
    ' Launch a new browser window
    Manager.LaunchNewBrowser(BrowserType.InternetExplorer)
 
    ' Add our HTTP response event handler
    Dim li As New ResponseListenerInfo(AddressOf CheckTypeForImage)
    Manager.Http.AddBeforeResponseListener(li)
 
    ' Navigate to a website containing images
    ActiveBrowser.NavigateTo("http://news.google.com/")
 
    ' We don't need the event handler any longer
    Manager.Http.RemoveBeforeResponseListener(li)
End Sub
 
Private Sub CheckTypeForImage(ByVal sender As Object, ByVal e As HttpResponseEventArgs)
    Log.WriteLine([String].Format("Request for {0}", e.Response.Request.RequestUri))
    If e.Response.IsImage Then
        Log.WriteLine([String].Format("Image detected; MIME type: {0}", e.Response.Headers("Content-Type")))
    Else
        Log.WriteLine([String].Format("Not an image; MIME type: {0}", e.Response.Headers("Content-Type")))
    End If
End Sub
````

Let's go one step further. Suppose we want to verify that all of the images on the web page were smaller than 40Kb. We can accomplish this using code like this:

````C#
[TestMethod]
public void CheckImageSize()
{
    // Add our HTTP response event handler
    ResponseListenerInfo li = new ResponseListenerInfo(Check);
    Manager.Http.AddBeforeResponseListener(li);
 
    // Launch a new browser window
    Manager.LaunchNewBrowser();
 
    // Navigate to a website containing images
    ActiveBrowser.NavigateTo("http://my.homepage.com/");
 
    // Check our global flag
    Assert.IsFalse(_imageTooLarge, "Some images in page >40k");
}
 
private volatile bool _imageTooLarge = false;
private void Check(object sender, HttpResponseEventArgs e)
{
    if (e.Response.IsImage && Int32.Parse(e.Response.Headers["Content-Length"]) > 40000)
    {
        _imageTooLarge = true;
    }
}
````
 

````VB
<TestMethod()> _
Public Sub CheckImageSize()
    ' Add our HTTP response event handler
    Dim li As New ResponseListenerInfo(AddressOf Check)
    Manager.Http.AddBeforeResponseListener(li)
 
    ' Launch a new browser window
    Manager.LaunchNewBrowser()
 
    ' Navigate to a website containing images
    ActiveBrowser.NavigateTo("http://my.homepage.com/")
 
    ' Check our global flag
    Assert.IsFalse(_imageTooLarge, "Some images in page >40k")
End Sub
 
Private _imageTooLarge As Boolean = False
Private Sub Check(ByVal sender As Object, ByVal e As HttpResponseEventArgs)
    If e.Response.IsImage AndAlso Int32.Parse(e.Response.Headers("Content-Length")) > 40000 Then
        _imageTooLarge = True
    End If
End Sub
````

**Note:** If you are using **localhost** in the URL of the **NavigateTo** method it must contain a trailing '.' character like this: ActiveBrowser.NavigateTo("http://localhost./myTestPage") . This is an IE limitation where all URL's must contain a '.' character in them to be recognized properly when a proxy is in place.