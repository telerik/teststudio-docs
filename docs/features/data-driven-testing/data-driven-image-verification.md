---
title: Data Driven Image Verification
page_title: Data Driven Image Verification
description: "Is there a way to data drive an image verification in Test Studio test?"
position: 12
---
# Data Driven Image Verification #

To data bind an <a href="/features/recorder/verifications/image-verification" target="_blank">image verification</a> step certain actions have to be performed. An approach to this scenario is to have previously stored histograms of the image element to which verification should be bonded. Then in a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> the verification has to be managed as it is given in the sample below:

```C#
// get an image of MyImage element        
System.Drawing.Bitmap bitmap = Pages.MyPage.MyImage.Capture();

// create a histogram to compare
ArtOfTest.Common.Histogram histogram = ArtOfTest.Common.Histogram.FromBitmap(bitmap);
// create Histogram to place original data inside
ArtOfTest.Common.Histogram histogramToCompare = ArtOfTest.Common.Histogram.FromBitmap(bitmap);

// place data from Data Source to a string array
var stringHistogram = Data["Histogram"].ToString().Split(',');

// place original data in the Histogram object
for (int i=0; i < histogram.Data.Length; i++)
{
    histogramToCompare.Data[i] = Double.Parse(stringHistogram[i]);
}
// compare histogram objects
double compareValue = (histogram.Compare(histogramToCompare) * 100);

// set tolerans in %
double tolerance = 10D;

// Assert statement 
ArtOfTest.Common.UnitTesting.Assert.IsTrue(tolerance >= compareValue); 
```
```VB

Dim bitmap As System.Drawing.Bitmap = Pages.MyPage.MyImage.Capture()

Dim histogram As ArtOfTest.Common.Histogram = ArtOfTest.Common.Histogram.FromBitmap(bitmap)

Dim histogramToCompare As ArtOfTest.Common.Histogram = ArtOfTest.Common.Histogram.FromBitmap(bitmap)

Dim stringHistogram = Data("Histogram").ToString().Split(","C)

For i As Integer = 0 To histogram.Data.Length - 1
	histogramToCompare.Data(i) = [Double].Parse(stringHistogram(i))
Next

Dim compareValue As Double = (histogram.Compare(histogramToCompare) * 100)

Dim tolerance As Double = 10.0

ArtOfTest.Common.UnitTesting.Assert.IsTrue(tolerance >= compareValue)
```

To complete this scenario using the provided sample:

- *System.Drawings* .NET assembly has to be <a href="/features/coded-steps/add-assembly-reference" target="_blank">referred</a> to the project
- test script has to be data-binded to a data source with *Histogram* column 
- image histogram data has to be placed as a single line string in the data storage cell. For a hystogram example - one is created if an image verification step is recorded in the test script .tstest file
