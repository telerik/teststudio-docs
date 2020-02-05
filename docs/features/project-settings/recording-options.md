---
title: Recording Settings
page_title: Recording Settings
description: "Test Studio project settings recording settings. Use the Test Studio recording settings to configure how recording will take place. Highlighting border adjustment in Test Studio recording. Set BaseURL for a project in Test Studio. How newly recorded pages are compared to the existing pages and their URL in Test Studio. The same element is recorded In Test Studio for each new recording session under different page node. Set default Record Drop-Down Option in Test Studio - by index, by value, by text. Enable/Disable Storyboard in Test Studio. Set Simulate Real Clicks/Typing By Default in Test Studio. Test Studio allow you to choose a custom name each time a new element is manually added to the Elements repository. Enable/Disable translator optimization during recording"
position: 2
---
# Recording Options

Use Recording section to configure how recording will take place. Some of the options are only needed for very specialized circumstances.

![Recording Options][1]

## Highlighting

The "Automation Overlay Surface" defines the highlight border color, border width and the amount of time before the Elements Menu displays.<br>

Click the **Border button** to display a color selector and use the sliders to adjust **Highlight Border Width** and **Menu Hold Time**. Delaying the Elements Menu display can be helpful if you're trying to hover the mouse and the Elements Menu is popping up too quickly.

![Highlighting][2a]

## BaseURL

Use this field if you run tests against multiple environments. Please see our <a href="/knowledge-base/test-execution-kb/base-url" target="_blank">BaseURL KB article</a> for more information.

> As of version **R1 2016** **BaseUrl** and **Compare Mode** can be set directly from the <a href="/getting-started/test-execution/quick-execution" target="_blank">Test ribbon</a>.

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

## Default DropDown Record Option

This setting determines the SelectDropDownType property value that will be used when recording selections in a drop-down control. Possible values are ByText, ByValue and ByIndex.

> **Note:** This option concerns only the **Html Select** element and does not apply to any elements structure that looks like a dropdown in the browser.

## Simulate Real Clicks/Typing By Default

By default, clicks and typing are recorded as sending clicks or text directly to the element. Setting these options will cause clicks and typing to be simulated by sending Windows events.

## Element Repository

If turned on, Test Studio will display a dialog for a custom name each time a new element is manually added to the repository. This is done from the <a href="/features/elements-menu/overview" target="_blank">Elements Menu</a> or the <a href="/features/elements-menu/dom-explorer" target="_blank">DOM Explorer</a> context menu.

![Add Element][3]

## Translators Optimization

This option allows you to stop the optimization the usage of <a href="/getting-started/test-recording/translators" target="_blank">translators</a> during recording. By default, Test Studio <a href="/features/project-settings/translators" target="_blank">enables only the translators</a>, which are useful for the page under test, depending on what controls it is built of. If the option is enabled, all translators will be enabled in the project settings and this may slow down the recording experience.

[1]: /img/features/project-settings/recording-options/fig1.png
[2]: /img/features/project-settings/recording-options/fig2.png
[3]: /img/features/project-settings/recording-options/fig3.png

[2a]: /img/features/project-settings/general/fig2.png
