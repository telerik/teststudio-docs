---
title: Add Tag to iFrame
page_title: Add Tag to iFrame | Test Studio Dev Documentation
description: Add Tag to iFrame
position: 1
---
# Add Tag to iFrame #

To help Test Studio Dev locate your _iframes_, you can add a custom tag to the iframe. You can then add this tag to the <a href="/features/recorder/specific-recording-scenario/frames" target="_blank">frame properties</a> in your test. There are two ways to add a tag to an iframe:

* Add the tag in the HTML for the target page

* Add the tag dynamically in a <a href="/code-in-test/features-in-code#Coded-Step" target="_blank">coded step</a>.

## Add a Tag to a iframe in HTML ##

To add a tag to a iframe in your application's HTML, add the 'testStudioTag' attribute to the frame element. For example:

```HTML
<iframe src="http://www.example.com" testStudioTag="ExampleTag"></iframe>
```

## Add a Tag Dynamically in Code ##

If it is not possible to add custom tags to your iframes, you can add them at runtime using a coded step.

1. Add the following using directive to your ode-behind file:

#### __[C#]__

		{{region }}

		using ArtOfTest.WebAii.Design.Extensions;
		{{endregion}}

2. Call the **myFrame()** method on the frame object in a coded step. For example:

#### __[C#]__

	{{region }}

		[CodedStep(@"Tag Frame with 'MyCustomTag'")]
		public void WebTest1_CodedStep()
		{
			Browser myFrame = this.ActiveBrowser.Frames[0] as Browser;
			if (myFrame != null )
			{
				myFrame.TagFrame("MyCustomTag");
			}          
		}
		{{endregion}}

To tag a nested iframe, ensure the entire DOM is built, so that Test Studio Dev can access the iframes. For example:

#### __[C#]__

	{{region }}	

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
	{{endregion}}

__See also:__

* <a href="/features/recorder/specific-recording-scenario/frames" target="_blank">Recording Frames</a>