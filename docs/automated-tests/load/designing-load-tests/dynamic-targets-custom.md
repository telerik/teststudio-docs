---
title: Dynamic Targets - Custom
page_title: Dynamic Targets - Custom
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 8
published: false
---
# Custom Dynamic Targets

Based on the HTTP traffic there might be targets which are not detected by Test Studio as dynamic but still these will be required to accomplish meaningful scenario. Or any of the auto-detected dynamic targets is not listed for transfer to a desired request.

To handle such scenarios Test Studio implemented the ability to add __Custom Dynamic Targets__. The Custom Dynamic Targets are available in the _Choose Dynamic Targets_ view where all auto-detected are listed as well - once a <a href="/features/testing-types/load-testing/capturing-traffic" target="_blank">user profile is captured</a> or opened <a href="/features/testing-types/load-testing/modifying-tests" target="_blank">to be modified</a> click the ___Choose Dynamic Targets___ button. 

![Choose Dynamic Targets][5]

Once any custom targets are added to the user profile these will be displayed under the list with all auto-detected dynamic targets. To add a custom dynamic target use the ___Add Dynamic Target___ button. 

![Add Dynamic Targets][6]

## Source Section Properties

- **Step**: Step to take the target from. Any step which contains a HTTP request can be selected. The Think time steps are filtered out and not displayed in the dropdown.
- **Response**: Which part of the HTTP response to be used - Body, Headers or Cookie. Select the necessary part of the HTTP response and verify its content.
- **Content**: Displays the content of the selected response part.
- **Search Type**: The type of search to be used in the content of the selected response - FullText, Regex, JSON, XML. Select any of the provided options to search for the necessary value from the response.
- **Starts after/before|Regex|JSON path|XPath**: Provide the search query to locate the desired value in the response.
- **Search Result**: Click to show the reuslt based on the search query.
- **Current Value**: Display the current reuslt based on the search query.

<table id="no-table">
	<tr>
		<td>__Source Body__<br>![Source Section Properties][7]</td>
		<td>__Source Headers__<br>![Source Section Properties][8]</td>
    </tr>
    <tr>
        <td>__Source Cookie__<br>![Source Section Properties][9]</td>
	</tr>
<table>

### Search Options

- ___FullText___ - use strings which surround the desired value to locate it in response. 

__Example:__ The head section of a HTTP response's body is:


```
<html>
<head><title>Example ASP Scripts</title></head>
```

To get the actual title you may use __Starts after:__ \<title\> and __Ends before:__ \</title\>

- ___Regex___ - use <a href="https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference" target="_blank">regular expression</a> to locate the desired value in response body, header or cookie.

> __Note!__ Test Studio uses \<val\> to express the first match in response!

__Example:__ The cookie of a HTTP response is the following string and the requirement is to get the domain name value only:

```
_EDGE_S=SID=04D5974D8509631807D39B2484BF62E4; path=/; httponly; domain=bing.com
```

The only possible approach is to use the partial search using Regex. The standard regex for extracting the desired value looks like this:

```
domain=(.*?)$
```


This returns the following match information:


```
Full match	65-80	`domain=bing.com`
Group 1.	72-80	`bing.com`
```

Using that standard regular expression in Test Studio will return the _Full match_ instead the value in _Group 1_. Therefore Test Studio uses \<val\> to express the first match group and the regular expression becomes:


```
domain=(?<val>.*?)$
```


- ___JSON___ - use <a href="http://goessner.net/articles/JsonPath/index.html#e3" target="_blank">JSONPath</a> to locate the desired value in response.

- ___XML___ - use <a href="https://msdn.microsoft.com/en-us/library/ms256122(v=vs.110).aspx" target="_blank">XPath</a> to locate the desired value in response.

## Destination Section Properties


- **Step**: Step to pass the target to. Any step that follows the selected one for source and contains a HTTP request could be selected for destination step. The Think time steps are filtered out and not displayed in the dropdown.
- **Field Type**: In what part of the HTTP request to include the custom dynamic target - Query Paramater, Header, Cookie, POST data, URL.
- **Field Name**: The name of the dynamic target which will be used in the HTTP request.

![Destination Section Properties][10]

## Important Notes

> __Note!__ The custom dynamic value will be added to the destination HTTP request even if there is no such parameter, cookie or header existing in the recorded request.
<br>
> __Note!__ If there are both autodetected and custom dynamic values for a single destination step, the last set target will be used in the request. Disable/Enable of a dynamic target will update the order of set targets. 
<br>
> __Note!__ As of now there is no visual representation for any custom dynamic targets within the __Edit User Profile__ view. To verify if the HTTP requests are built as you expect you could use <a href="https://www.telerik.com/fiddler" target="_blank">Fiddler</a> to capture the traffic of a sample load test execution and inspect these.

[1]: /img/features/testing-types/load-testing/dynamic-targets/fig1.png
[2]: /img/features/testing-types/load-testing/dynamic-targets/fig2.png
[3]: /img/features/testing-types/load-testing/dynamic-targets/fig3.png
[4]: /img/features/testing-types/load-testing/dynamic-targets/fig4.png
[5]: /img/features/testing-types/load-testing/dynamic-targets/fig5.png
[6]: /img/features/testing-types/load-testing/dynamic-targets/fig6.png
[7]: /img/features/testing-types/load-testing/dynamic-targets/fig7.png
[8]: /img/features/testing-types/load-testing/dynamic-targets/fig7a.png
[9]: /img/features/testing-types/load-testing/dynamic-targets/fig7b.png
[10]: /img/features/testing-types/load-testing/dynamic-targets/fig8.png
