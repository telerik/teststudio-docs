---
title: Add Tag to iFrame
page_title: Add Tag to iFrame
description: "Learn how to add custom tags to iframes in Test Studio, either by modifying HTML or dynamically through coded steps, to improve frame identification during automated testing."

position: 1
---
# Add Tag to iFrame 

To help Test Studio locate your iframes, you can add a custom tag to the iframe. You can then add this tag to the <a href="/getting-started/test-recording/Frames" target="_blank">frame properties</a> in your test. There are two ways to add a tag to an iframe:

* Add the tag in the HTML for the target page

* Add the tag dynamically in a <a href="/features/custom-steps/script-step" target="_blank">coded step</a>.

##Add a Tag to a iframe in HTML##

To add a tag to a iframe in your application's HTML, add the 'testStudioTag' attribute to the frame element. For example:

```HTML
<iframe src="http://www.example.com" testStudioTag="ExampleTag"></iframe>
```

## Add a Tag Dynamically in Code 

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

## See Also 

* <a href="/getting-started/test-recording/Frames" target="_blank">Recording Frames</a>