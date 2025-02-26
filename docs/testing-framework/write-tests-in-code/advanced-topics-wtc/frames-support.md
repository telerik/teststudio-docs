---
title: Frames Support
page_title: Frames Support
description: "Test Studio Testing Framework support for iFrames. Access elements in iFrames from a coded step. Coded test to interact with elements in iFrames. "
position: 1
---
# Frames Support

Telerik Testing Framework understands what Frames and IFrames are and includes built-in support to work with them. It automatically scans the webpage and locates all of the frames it contains and then adds them to the FramesCollection property of the Browser object.
 
Frames are treated just like another browser instance. In order to work with the elements contained in a frame you must first obtain the browser instance that holds the frame you want. You can do this in one of the following ways:

<table class="docs">
<tr>
	<th>Method</th><th>Parameter</th><th>Description</th>
</tr>
<tr>
	<td>**Browser.Frames[string frameName]**</td>
	<td>Takes a string that specifies the name of the frame. e.g. <frame src="t1.html" name="t1_frame"></td>
	<td>This method searches for a frame that matches the specified string and then returns a Browser object representing that frame that you can use to interact with the frame. Returns null if no matching frame can be found.</td>
</tr>
<tr>
	<td>**Browser.Frames[int frameIndex]**</td>
	<td>Takes an integer specifying which frame to get from the frame collection. Useful if you know ahead of time you want the second frame. e.g. ActiveBrowser.Frames[1]</td>
	<td>This method searches for a frame that matches the specified string and then returns a Browser object representing that frame that you can use to interact with the frame. Throws an error if the index value is out of range.</td>
</tr>
<tr>
	<td>**Browser.Frames[FrameInfo frameInfo]**</td>
	<td>Takes a FrameInfo object that specifies the properties of the frame you want. Perhaps you want to locate a frame by its src property.</td>
	<td>This method searches for a frame that matches the specified string and then returns a Browser object representing that frame that you can use to interact with the frame. Returns null if no matching frame can be found.</td>
</tr>
<tr>
	<td>**Browser.Frames.ById(string frameId)**</td>
	<td>Takes a string that specifies the ID of the frame. Prefix with a tilde (~) to indicate a partial match.</td>
	<td>This method searches for a frame that matches the specified string and then returns a Browser object representing that frame that you can use to interact with the frame. Returns null if no matching frame can be found. </td>
</tr>
<tr>
	<td>**Browser.Frames.BySrc(string src)**</td>
	<td>Takes a string that specifies the source of the frame. Prefix with a tilde (~) to indicate a partial match.</td>
	<td>This method searches for a frame that matches the specified string and then returns a Browser object representing that frame that you can use to interact with the frame. Returns null if no matching frame can be found. </td>
</tr>
</table>

Telerik Testing Framework allows users to access frames and perform automation against these frames just like any other page. A frame is simply a mini browser window inside your web page that can host its own HTML document. That is why frames are represented as Browser objects and are accessible using the **Frames[]** collection of the browser object that contains the 'iframe' or 'frameset' elements.
 
Let's take an example that demonstrates this support. Assuming we have the following simple web page:

````HTML
<HTML>
<HEAD><TITLE>THE I HATE FRAMES PAGE</TITLE></HEAD>
<FRAMESET COLS="33%,33%">
    <FRAMESRC="t1.html" name="T1_Frame">
    <FRAMESRC="..\BrowserActions.htm" id="T2_Frame">
</FRAMESET>
</HTML>
````

To access the 't1.html' frame elements and perform actions against it, first I need to navigate to the page, then I need to access the frame that contains that page from the 'Frames[]' collection as follows:

````C#
// Launch an instance of the browser
Manager.LaunchNewBrowser(BrowserType.InternetExplorer, true);
   
// Navigate to the test page
ActiveBrowser.NavigateTo(TESTPAGE);
   
// Access a frame
//
// NOTE: The Frames collection contains a flat list of all
// frames on the page regardless of their nesting.
ArtOfTest.WebAii.Core.Browser t1_frame = ActiveBrowser.Frames["T1_Frame"];
ArtOfTest.WebAii.Core.Browser t2_frame = ActiveBrowser.Frames.ById("T2_Frame");
   
// Find the elements on the page using the Find.BYxxx methods.
Element toggleOn = t1_frame.Find.ById("btn1");
Element toggleOff = t2_frame.Find.ById("btn2");
   
// Now click the toggleOn button.
t1_frame.Actions.Click(toggleOn);
   
// Click the toggleoff button
t2_frame.Actions.Click(toggleOff);
````
````VB
' Launch an instance of the browser
Manager.LaunchNewBrowser(BrowserType.InternetExplorer, True)
 
' Navigate to the test page
ActiveBrowser.NavigateTo(TESTPAGE)
 
' Access a frame
'
' NOTE: The Frames collection contains a flat list of all
' frames on the page regardless of their nesting.
Dim t1_frame As ArtOfTest.WebAii.Core.Browser = ActiveBrowser.Frames("T1_Frame")
Dim t2_frame As ArtOfTest.WebAii.Core.Browser = ActiveBrowser.Frames.ById("T2_Frame")
 
' Find the elements on the page using the Find.BYxxx methods.
Dim toggleOn As Element = t1_frame.Find.ById("btn1")
Dim toggleOff As Element = t2_frame.Find.ById("btn2")
 
' Now click the toggleOn button.
t1_frame.Actions.Click(toggleOn)
 
' Click the toggleoff button
t2_frame.Actions.Click(toggleOff)
````

At this point, the 't1_frame' object is just like any other Browser object. You can use the Find.Byxxx/Actions objects to find elements/execute actions in the document or execute any of the browser actions like 'NavigateTo' or 'Refresh()', 'GoBack()', etc.
 
### Notes about Frames support:

The Frames collection supports two methods that can be used to easily wait on all frames to be ready or to refresh all the DOM trees within these frames. The methods are : 'ActiveBrowser.Frames.RefreshAllDomTrees()' & 'ActiveBrowser.Frames.WaitAllUntilReady()'. You can use these methods if you are doing actions that affect all frames in the page and you want to wait for these actions across all frames all at once