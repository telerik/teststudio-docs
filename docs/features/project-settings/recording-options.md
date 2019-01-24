---
title: Recording
page_title: Recording
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/project-settings/recording-options.aspx, /user-guide/project-settings/recording-options
position: 2
---
# Recording

Use Recording section to configure how recording will take place. Some of the options are only needed for very specialized circumstances.

![Recording Options][1]

> As of version **R1 2016** **BaseUrl** and **Compare Mode** can be set directly from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Test ribbon</a>.

## BaseURL

Use this field if you run tests against multiple environments. Please see our <a href="/knowledge-base/test-execution-kb/base-url" target="_blank">BaseURL KB article</a> for more information.

## Elements Page Compare Mode

This setting determines the Compare Mode property to use when adding a page node to the Elements Explorer. Compare Mode can be checked against the page's Title or one of multiple settings that look at various parts of a URL. The screenshot below shows the parts of a URL:

- The BaseURL is the part of the URL before the first "/".
- The Path is the part of the URL after the Base and before the Query.
- The Query is the portion after the "?" and before the "#".
- The "#" marks the beginning of the Fragment portion of the URL, if present.

![URL][2] 

Consider the following three URLs:

- http://www.google.com/translate/?hl=en#de|en|hungry
- http://www.google.com/translate/?hl=en#de|en|money
- http://www.google.com/translate/?hl=fr#de|en|money

 
Here's how these URLs would break out into Page nodes in the Elements Explorer with the following Compare Mode options:

**BaseURL**

- Compared portion of URL: http://www.google.com
- Result: All three would be the same page.

**FullPath**

- Compared portion of URL: http://www.google.com/translate
- Result: All three would be the same page.
    
**FullPathAndQuery**

- Compared portion of URL: http://www.google.com/translate/?hl=en#de|en|hungary
- Result: All three would be separate pages, since each URL is different from the others. (Query and Fragment portions differ.)

**FullPathAndQueryNoFragment**

- Compared portion of URL: http://www.google.com/translate/?hl=en
- Result: The first two URLs would be one page (the Query is the same: "?hl=en"), and the third would be a separate page. (Query has a different language.)

The **Relative** options work the same however, they ignore the www.google.com portions of the URL, so two different sites with the same Path, Query, and Fragment would end up as the same page. 

> This works only when a **BaseURL** is set!

For example:
        
- http://www.google.com/translate/?hl=en#de|en|money
- http://teststudio.net/translate/?hl=en#de|en|money


The **Title** option only uses the page title for comparison and ignores the URL entirely.

## Code Base Class

This option allows you to create and use a specialized test class. For example, you could create a class that knows how to log to your corporation's database. The code-behind for a Test Studio test uses "BaseWebAiiTest" by default. BaseWebAiiTest is an object that knows how to execute test steps, find elements on a page, perform actions against all browser types (i.e. click, scroll, etc) and log test results. BaseWebAiiTest also keeps track of the active browser and the test data.

## SL Connect Timeout

The amount of time in milliseconds to wait for Test Studio to connect to a Silverlight application.


## Default DropDown Record Option

This setting determines the SelectDropDownType property value that will be used when recording selections in a drop-down control. Possible values are ByText, ByValue and ByIndex. 
This option concerns only the **Html Select** element and does not apply to any elements structure that looks like a dropdown in the browser.

## Enable Storyboard

By default, screenshots are automatically added to the Storyboard Tab. When this option is unchecked, a placeholder image is used. Uncheck the option when you want to conserve memory and disk space. The Scale slider adjusts the size of the Storyboard Tab between "10%" and "100%".

## Simulate Real Clicks/Typing By Default

By default, clicks and typing are recorded as sending clicks or text directly to the element. Setting these options will cause clicks and typing to be simulated by sending Windows events.

## Element Repository

If turned on, Test Studio will display a dialog for a custom name each time a new element is manually added to the repository. This is done from the <a href="/features/elements-menu/overview" target="_blank">Elements Menu</a> or the <a href="/features/elements-menu/dom-explorer" target="_blank">DOM Explorer</a> context menu.

![Add Element][3]

[1]: /img/features/project-settings/recording-options/fig1.png
[2]: /img/features/project-settings/recording-options/fig2.png
[3]: /img/features/project-settings/recording-options/fig3.png


