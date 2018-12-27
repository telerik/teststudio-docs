---
title: jQuery Events Do Not Fire
page_title: jQuery Events Do Not Fire | Test Studio Dev Documentation
description: jQuery Events Do Not Fire
position: 1
---
# jQuery Events Do Not Fire During Test Execution 

In some cases, Test Studio Dev does not automatically call local jQuery events. You must add a coded step to make the local jQuery event fire manually.

Inputting text into <a href="http://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_event_change" target="_blank">this</a> simple HTML text box triggers a jQuery event that changes the background color of the text box.

<table id="no-table">
	<tr>
		<td>![Before Selection][1] </br></br>**Before Selection**</td>
		<td>![Available Selections][2] </br></br>**Available Selections**</td>
		<td>![After Selection][3] </br></br>**After Selection**</td>
	</tr>
<table>

This is the HTML for the text input element:

```HTML
Enter your name: <input class="field" type="text">
```
Invoke the script that changes the background color with the following coded step:

#### __[C#]__

	{{region }}

	Pages.TryitEditorV220.FrameIframeResult.Text.AsjQueryControl().InvokejQueryEvent(ArtOfTest.WebAii.jQuery.jQueryControl.jQueryControlEvents.change);
	{{endregion}}

* The guideline is to always pair the two steps together. Immediately after performing the change step (input, radio button, etc.), run the coded step that calls the .change function for that element.

* Although *.change* is the most frequent <a href="http://api.jquery.com/category/events/" target="_blank">jQuery event</a>, your application might be attaching to a different event. Another common example is .select. If those two do not work, ask your developers which jQuery event is attached to the element.

* If you have a choice between using id and name of an element, we recommend using id. It is usually a unique value which will make your tests run more reliably. Name is sometimes duplicated, which can cause your test to find and act against the wrong element, since the selector will act on the first element it finds matching the selector criteria.

[1]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig1.png
[2]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig2.png
[3]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig3.png
