---
title: Navigate To
page_title: Navigate To
description: "How to navigate to a page in Test Studio? Can I add a step to navigate to a page in the middle of the test in Test Studio"
position: 1
---

# Navigate To Step 

The __Navigate To__ step allows you to insert a step which navigates to specified URL.

This article demonstrates how to add this type of step into the test and the specifics of its properties.

- [Add Navigate To Step](#add-navigate-to-step)
- [Using BaseURL on Project Level](#using-baseurl-on-project-level)

## Add Navigate To Step

Choose the __Navigate To__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Navigate To](/img/features/custom-steps/navigate-to/fig1.png)

The __Navigate To__ accepts a valid URL. The step gets automatically recorded when you begin recording a test. You can insert such step at any point of the test from the __Step Builder__ or record one from the <a href="/features/recorder/advanced-recording-tools/browser-control" target="_blank">__Browsers tab__</a> in the __Advanced Recording Tools__.

Other useful properties of the step are:

* __NavigateUrl__ - defines the navigate URL, or the part of the URL which is different from the BaseUrl.
* __BaseUrl__ -  defines the BaseUrl itself.

## Using BaseURL on Project Level

Test Studio allows <a href="/knowledge-base/test-execution-kb/base-url" target="_blank">setting up a project for running tests against multiple environments</a>. If using such setup there are few important notes about the __Navigate To__ steps across the tests.

1. The __Navigate To__ step has two properties related to the URL to be used - the __NavigateUr__, which defines the part of the URL which is different from the BaseUrl,  and the __BaseUrl__, which defines the BaseUrl itself.

    __Example__: If using the `https://docs.telerik.com/teststudio/system-requirements` for testing, it can be split to _BaseUrl_: `https://docs.telerik.com/teststudio` and _NavigateUrl_: `/system-requirements`.

    > __Note!__
    ><br>
    ><br>
    >  When the __BaseUrl__ property of the __Navigate To__ step is set, it is always used upon execution, or in other words it overwrite the project and test list settings for the multiple environments setup of the project.

2. If the <a href="/features/project-settings/recording-options" target="_blank">project setting __BaseUrl__ is set</a>, it is used in the following manner: Upon execution the __Navigate To__ step property _NavigateUrl_ is appended to the project set _BaserUrl_ (assuming the step's _BaseUrl_ property is empty).

3. If the <a href="/features/test-lists/test-list-settings#web-tab" target="_blank">test list setting</a> __BaseUrl__ is set, it is used in the following manner: Upon execution the __Navigate To__ step property _NavigateUrl_ is appended to the test list set _BaserUrl_ (assuming the step's _BaseUrl_ property is empty).

4. The step property BaseUrl allows you to use relative Url with the the tilde sign (~).

    __Example__: Possible setup described below

    * Project BaseUrl set to `https://docs.telerik.com/teststudio`
    * Step property _NavigateUrl_ is set to `/first-test`
    * Step property _BaseUrl_ is set to `~/getting-started`
    * The final URL to navigate to is `https://docs.telerik.com/teststudio/getting-started/first-test`
