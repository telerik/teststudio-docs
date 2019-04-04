---
title: Silverlight OOB and Elevated Trust
page_title: Silverlight OOB and Elevated Trust
description: Silverlight OOB and Elevated Trust
position: 1
---
# Silverlight OOB and Elevated Trust

From Silverlight 5 and above we do not support true OOB with ElevatedTrust. If you run the app. as OOB in browser the ElevatedTrust will remain and the app. will function.

In order to overcome this problem you have to manually include the needed dlls and update the "AppManifest.xml" so Test Studio will not need to inject them.

How to proceed:

1. Three additional dlls should be present in the *.xap file:

	![References][1]

* **ArtOfTest.SLExtension.dll** is something we ship so it should be in the “(install)\Bin” folder

* **Telerik.WebAii.Controls.Xaml.CustomTypes.dll** should be in the “(install)\Bin\Translators\CustomSilverlightTypes” folder

* **System.Windows.dll** is part of the SL framework but the reference needs to be with “CopyLocal” option set to “True” so it is included in the xap

2. In the “AppManifest.xml” the “ExternalCallersFromCrossDomain” should be set to “ScriptableOnly” as shown below:

	![AppManifest][2]

[1]: /img/knowledge-base/silverlight-kb/silverlight-oob-and-elevated-trust/fig1.png
[2]: /img/knowledge-base/silverlight-kb/silverlight-oob-and-elevated-trust/fig2.png