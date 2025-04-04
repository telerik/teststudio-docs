---
title: Silverlight Highlighting
page_title: Hover Over Highlighting Not Recognizing Individual Silverlight Elements
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# Hover Over Highlighting Not Recognizing Individual Silverlight Elements

## PROBLEM

Hover over highlighting does not recognize individual Silverlight elements in your application. Although accessible through the DOM, the recording surface only detects the Silverlight components as one object.

# SOLUTION

Set the *windowless* parameter for your Silverlight application to true:

	<object id="xamlHost0" width="900" height="412" type="application/x-silverlight">
    <param value="transparent" name="background"/>
    <param value="true" name="windowless"/>
    <!-- other params go here -->
	</object>

Here is the technical problem that causes this behavior and why/how setting the *windowless* parameter to true helps:

The default behavior is for IE to create a separate real Win32 window (with no border/chrome) and render the Silverlight application within this real window. This window is overlaid on top of the `<object>` tag being rendered within the browser window such that they should lay directly on top of one another. For Test Studio to attach to and control the Silverlight application, it must locate the correct Win32 window and hook into it. Test Studio locates the correct window by asking the browser for the screen coordinates of the `<object>` tag and then hooking into the Win32 window that overlays that location.

However, sometimes (we have yet to clearly understand when/why this happens) IE gives incorrect coordinates for where the `<object>` tag is being rendered within the browser window. It says it is located at position X (an incorrect position), but the window is actually at position Y. As a result, Test Studio is unable to find the Silverlight application window so that it can hook into it. This causes the behavior described above where the windowless parameter is set to the default setting of false.

By setting the windowless parameter to true, IE renders the Silverlight application directly in the browser window. Test Studio detects this property setting and injects its Silverlight hooks into the IE browser window when seen instead of looking for a separate Win32 window. Thus, even though IE may give incorrect coordinates for the `<object>` tag, Test Studio is no longer sensitive to it.


We don't know when/why IE sometimes gives incorrect screen coordinates for the `<object>` tag. When it does, setting the windowless parameter to true is the only solution. Different versions of IE may behave differently, and turning on/off Quirks mode may also change the behavior of IE in this area.