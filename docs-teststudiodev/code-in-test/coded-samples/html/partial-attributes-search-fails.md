---
title: Partial Attributes Search Fails
page_title: Partial Attributes Search Fails - Test Studio Dev Documentation
description:  Partial Attributes Search Fails
position: 1
---
# Partial Attributes Search by Control Type Fails #

_A partial search of control by attribute may return null even with correct partial search syntax._

For example a HtmlInputButton search on the page having a complex ID containing some specific string should be located successfully using the following syntax:

#### __[C#]__

    {{region }}

    HtmlInputButton button = Find.ById<HtmlInputButton>("~MyButtonIDPart");
    {{endregion}}

Although the next example works as well:


#### __[C#]__

    {{region }}

    HtmlInputButton button = Find.ById<HtmlInputButton>("SomeButtonIDPart_MyButtonIDPart");
    {{endregion}}

## Notes ##

The framework locates the first element matching the given attribute search criteria. Next, it compares the control type of the element and returns that element if the control type matches. If it does not, it simply returns null.

In the first example, the framework returns null if there is another element that matches the given attribute search criteria and it is found before the target element. The control type does not match.

## Solution ##

A simple solution is available. Use Find.AllByAttributes<Control Type> overload and return the first (and actually the only completely matching control):

#### __[C#]__

    {{region }}

    HtmlInputButton button = Find.AllByAttributes<HtmlInputButton>("id=~MyButtonIDPart")[0];
    {{endregion}}
