---
title: Element Validation
page_title: Element Validation
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 3
---
# Validating Properties of Silverlight Elements

```C#
Assert.IsTrue(guidanceOverlays.Count == 15);
Assert.IsTrue(CompareUtils.NumberCompareRange(foundPatients.Count, 93, 105, NumberRangeCompareType.InRange);
Assert.IsTrue(patientSearchItem.Find.ByName("Address").Visibility == Visibility.Collapsed);
Assert.IsTrue(searchScroll.VerticalOffset == 2000);
Assert.AreEqual<System.Drawing.Rectangle>(new System.Drawing.Rectangle(1700, 259, 813, 465), admin1.GetScreenRectangle());
```
```VB
app.Find.Strategy = FindStrategy.WhenNotVisibleReturnElementProxy
Assert.IsTrue(CompareUtils.NumberCompareRange(foundPatients.Count, 93, 105, NumberRangeCompareType.InRange))
Assert.IsTrue(patientSearchItem.Find.ByName("Address").Visibility = Visibility.Collapsed)
Assert.AreEqual(2000, searchScroll.VerticalOffset)
Assert.AreEqual(Of System.Drawing.Rectangle)(New System.Drawing.Rectangle(1700, 259, 813, 465), admin1.GetScreenRectangle())
```


