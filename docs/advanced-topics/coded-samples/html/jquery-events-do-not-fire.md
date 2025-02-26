---
title: jQuery Events Do Not Fire
page_title: jQuery Events Do Not Fire
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/jquery-events-do-not-fire.aspx, /user-guide/code-samples/html/jquery-events-do-not-fire
position: 1
---
# jQuery Events Do Not Fire During Test Execution

**Note:** As of 2012 R1 SP1, use the TriggerjQueryEvent <a href="/features/test-maintenance/test-step-properties" target="_blank">Test Step Property</a> to trigger jQuery events for HTML drop-down menus. Minimum supported jQuery version is 1.4.

In some cases, Test Studio does not automatically call local jQuery events. You must add a coded step to make the local jQuery event fire manually.

Inputting text into <a href="http://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_event_change" target="_blank">this</a> simple HTML text box triggers a jQuery event that changes the background color of the text box.

<table id="no-table" style="border:none;">
	<tr>
		<td style="text-align: center;">
		
![Before Selection][1] </br></br>**Before Selection**</td>
<td style="text-align: center;">

![Available Selections][2] </br></br>**Available Selections**</td>
<td style="text-align: center;">

![After Selection][3] </br></br>**After Selection**</td>

</tr>
</table>

This is the HTML for the text input element:

````HTML
Enter your name: <input class="field" type="text">
````


Invoke the script that changes the background color with the following coded step:

````C#
Pages.TryitEditorV220.FrameIframeResult.Text.AsjQueryControl().InvokejQueryEvent(ArtOfTest.WebAii.jQuery.jQueryControl.jQueryControlEvents.change);
````

* The guideline is to always pair the two steps together. Immediately after performing the change step (input, radio button, etc.), run the coded step that calls the .change function for that element.

* Although *.change* is the most frequent <a href="http://api.jquery.com/category/events/" target="_blank">jQuery event</a>, your application might be attaching to a different event. Another common example is .select. If those two do not work, ask your developers which jQuery event is attached to the element.

* If you have a choice between using id and name on an element, we recommend using id. It is usually a unique value which will make your tests run more reliably. Name is sometimes duplicated, which can cause your test to find and act on the wrong element, since the selector will act on the first element it finds matching the selector criteria.

Here are test steps recorded against the demo page above:

![Test][4]

Even there is no selection/typing in the field step 4 will triggers *.change* event and the input filed will become violet.

[1]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig1.png
[2]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig2.png
[3]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig3.png
[4]: /img/advanced-topics/coded-samples/html/jQuery-events-do-not-fire/fig4.png


