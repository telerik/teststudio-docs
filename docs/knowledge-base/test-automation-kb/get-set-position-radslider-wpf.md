---
title: Get or set the position of WPF RadSlider for WPF programatically
description: Learn how to get or set the position of WPF RadSlider for WPF programatically
type: how-to
page_title: Get or set the position of WPF RadSlider for WPF programatically
slug: get-set-position-radslider-wpf
tags: automation, WPF, RadSlider, Test Studio
res_type: kb
---

## Description
Getting or setting a slider position programatically from Test Studio may vary depending how the RadSlider control is defined in the application under test. 

## Solution
In the case when there is no explicitly defined slider thumb, you can use the Value property of the slider object.

Let's say that in the application under test there is a slider defined like this:

````xml
<telerik:RadSlider Name="MySlider" Minimum="0" Maximum="100" Value="50"/>
````

Use following Test Studio code to get/set the position of the slider in the application under test.

````C#
// Read value
var sliderValue = Applications.<YOUR_APPLICATION>.<YOUR_WINDOW>.MySlider.Find.ByType<SliderThumb>().Value;

// Change value
Applications.<YOUR_APPLICATION>.<YOUR_WINDOW>.MySlider.Find.ByType<SliderThumb>().Value = 20;
````

In the case when there is an explicitly defined slider thumb, you will have to use that thumb's Value property to change the position of the slider.

Let's say that in the application under test there is a slider defined like this:

````xml
<telerik:RadSlider Name="MySlider" Minimum="0" Maximum="100">
    <telerik:RadSlider.Thumbs>
        <telerik:SliderThumb Value="50" Visibility="Visible"/>
    </telerik:RadSlider.Thumbs>
</telerik:RadSlider>
````

Use following Test Studio code to get/set the possition of the slider in the application under test.

````C#
// Read value
var sliderValue = Applications.<YOUR_APPLICATION>.<YOUR_WINDOW>.MySlider.Find.ByType<SliderThumb>().Value;

// Change value
Applications.<YOUR_APPLICATION>.<YOUR_WINDOW>.MySlider.Find.ByType<SliderThumb>().Value = 20;
````