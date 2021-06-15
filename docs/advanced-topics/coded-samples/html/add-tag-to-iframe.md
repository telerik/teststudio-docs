---
title: Add Tag to iFrame
page_title: Add Tag to iFrame
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/tagframe.aspx, /user-guide/code-samples/html/tagframe
position: 1
---
#Add Tag to iFrame#

To help Test Studio locate your iframes, you can add a custom tag to the iframe. You can then add this tag to the <a href="/getting-started/test-recording/Frames" target="_blank">frame properties</a> in your test. There are two ways to add a tag to an iframe:

[frame properties colon](/getting-started/test-recording/Frames){:target="_blank"}

[frame properties no colon](/getting-started/test-recording/Frames){target="_blank"}

* Add the tag in the HTML for the target page

* Add the tag dynamically in a <a href="/features/custom-steps/script-step" target="_blank">coded step</a>.

##Add a Tag to a iframe in HTML##

To add a tag to a iframe in your application's HTML, add the 'testStudioTag' attribute to the frame element. For example:

```HTML
<iframe src="http://www.example.com" testStudioTag="ExampleTag"></iframe>
```

##Add a Tag Dynamically in Code##

If it is not possible to add custom tags to your iframes, you can add them at runtime using a coded step.

1. Add the following using directive to your <a href="/advanced-topics/coded-steps/code-behind-file" target="_blank">code-behind file</a>:

	```C#
	using ArtOfTest.WebAii.Design.Extensions;
	```

2. Call the **myFrame()** method on the frame object in a coded step. For example:

	```C#
	[CodedStep(@"Tag Frame with 'MyCustomTag'")]
	public void WebTest1_CodedStep()
	{
	    Browser myFrame = this.ActiveBrowser.Frames[0] as Browser;
	    if (myFrame != null )
	    {
	        myFrame.TagFrame("MyCustomTag");
	    }          
	}
	```

To tag a nested iframe, ensure the entire DOM is built, so that Test Studio can access the iframes. For example:

```C#
[CodedStep(@"Tag nested frame with 'MyCustomTag'")]
public void WebTest1_CodedStep()
{
    this.ActiveBrowser.Frames.RefreshAllDomTrees();
 
    Browser myFrame = this.ActiveBrowser.Frames[3] as Browser;
    if (myFrame != null )
    {
        myFrame.TagFrame("MyCustomTag");
    }           
}
```

##See also##

* <a href="/getting-started/test-recording/Frames" target="_blank">Recording Frames</a>