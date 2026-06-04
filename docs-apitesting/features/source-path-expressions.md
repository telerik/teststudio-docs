---
title: Source Path Expressions
page_title: Source Path Expressions
description: "Progress® Test Studio® for APIs - Source Path Expressions"
position: 0
published: true
---

# Source Path Expressions

## Overview

[Verifications](/features/verifications) and [Set Variable Steps](/features/steps/set-variable) both allow the user to specify a Source. 
The Source always references a [Variable](/features/variables) which should be used as the source of the value to be used for verification or extraction.

If you wish to use the full value of the source variable, you can use the **Full Value** option and use the value unmodified

![Full Value Path Option][1]

If the Source is a complex value (like a JSON or XML) and the user needs to use just a part of that value, one can use the Source Path field to extract the desired parts of the Source.
If the user needs to extract a part of a text that is not a JSON or XML, one can use a regular expression.

Test Studio for APIs supports **JSONPath**, **XPath** and **Regex** for path expressions.

![Source Path Type Options][2]

## XPath

Since version R1 2017, Test Studio for APIs supports XPath expressions. Here are some useful links where you can read more about the XPath syntax:
 - [w3schools](http://www.w3schools.com/xml/xpath_syntax.asp)
 - [msdn](https://msdn.microsoft.com/en-us/library/ms256471(v=vs.110).aspx)
 - [msdn](https://msdn.microsoft.com/en-us/library/ms256086(v=vs.110).aspx)

 Also see below for some [examples](#Examples).

## JSONPath

Test Studio for APIs supports basic JSONPath expressions. The original article, describing the JSONPath specification can be found [here](http://goessner.net/articles/JsonPath/). 
Note though that different JSONPath implementations cover that specification to a different extend and variation. 
Test Studio for APIs supports most but not all of the expressions described in the JSONPath specification. See [Current JSONPath Limitations](#Current-JSONPath-Limitations) below for more information.

 See below for some [examples](#Examples).

### Current JSONPath Limitations

There are certain limitations of the scenarios that can be achieved with JSONPath in Test Studio for APIs. 

 - The length of a JSON array cannot be retrieved using JSONPath (e.g.: $.users.length()). You can use a [Coded Step](/features/code-features/coded-steps) to parse a JSON value and get the length of its collection (you could add a [reference](/features/code-features/add-assembly-reference) to [Json.Net](http://www.newtonsoft.com/json) in your project and use it to parse the json value).
 - Test Studio for APIs currently does not support replacing property names or indexes with script expressions. For example such an expression would be: `$.store.book[(@.length-1)]`.
 A supported alternative of the last expression would be: `$.store.book[-1:]`. 


### Examples

As an example of the JSONPath expressions that are supported in Test Studio for APIs we will use the same book store example as provided in the [JSONPath specification](http://goessner.net/articles/JsonPath/index.html#e3).

```
{ 
    "store": {
        "book": [ 
            { "category": "reference",
                "author": "Nigel Rees",
                "title": "Sayings of the Century",
                "price": 8.95
            },
            { "category": "fiction",
                "author": "Evelyn Waugh",
                "title": "Sword of Honour",
                "price": 12.99
            },
            { "category": "fiction",
                "author": "Herman Melville",
                "title": "Moby Dick",
                "isbn": "0-553-21311-3",
                "price": 8.99
            },
            { "category": "fiction",
                "author": "J. R. R. Tolkien",
                "title": "The Lord of the Rings",
                "isbn": "0-395-19395-8",
                "price": 22.99
            }
        ],
        "bicycle": {
            "color": "red",
            "price": 19.95
        }
    }
}
```

|XPath|JSONPath|Result|
|---|---|---|
|/store/book/author|$.store.book[*].author|the authors of all books in the store|
|//author|$..author|all authors|
|/store/* | $.store.* |all things in store|
|/store//price|$.store..price|	the price of everything in the store|
|//book[3]|$..book[[2]]|	the third book|
|//book[last()]|$..book[-1:]|the last book in order (note that the "`$..book[(@.length-1)]`" expression is not supported in Test Studio)|
|//book[position()<3]|$..book[0,1] <br> $..book[:2]|the first two books|
|//book[isbn]|$..book[?(@.isbn)]|filter all books with isbn number|
|//book[price<10]|$..book[?(@.price<10)]|filter all books cheaper than 10|
|//*| $..* |all Elements in XML document. All members of JSON structure|

> Check the [Sample Project](/getting-started/sample-project) for more real-life examples of path expressions.

## Regex

You can use regular expressions in the **Path** field of **Set-Variable** steps or **Verifications** when you need to extract a portion of a variable's value. 

> When building your regular expressions, you should have in mind that Test Studio for APIs is based on .Net and therefore shares the framework's features and limitations in terms of regex processing. You can see [here](https://msdn.microsoft.com/en-us/library/az24scfc(v=vs.110).aspx) for a quick reference of the supported regex features. See [here](https://en.wikipedia.org/wiki/Comparison_of_regular_expression_engines#Language_features) for some comparison of the features, supported by .Net compared to other frameworks/languages.

### First Match Only

If more than one parts of your source match your regular expression, Test Studio for APIs will return only the first occurrence. If you need to extract some of the non-first occurrences of your match, you need to adjust your regular expression to match it first.

> Regular expressions will always be applied from left to right so you will get the left-most match of your pattern.

**Example:**

> If your Source contains the following string:

> `Lorem xxx111xxx ipsum xxx222xxx dolor sit amet xxx333xxx`

> The pattern: `xxx(\d{3})xxx`

> will return: `xxx111xxx`


### Extracting part of a regex match

If you need to extract only part of your match, you can use a [named group](https://msdn.microsoft.com/en-us/library/bs2twtah(v=vs.110).aspx#named_matched_subexpression) in your pattern (like "(?&lt;SomeGroupName&gt;\w*)"). You can set whatever name of the group you prefer. The only requirement for the Test Studio for APIs to detect that you want to extract only that group (instead of the full match) is to make it a named group with any name. If you have more than one named group in your regular expression, then only the first named group will be extracted. If you have no groups in your expression, or if all of them are unnamed parentheses, then the full match of your pattern will be extracted.

**Example:** If you want to extract an id_token for example from a Location header like this:

    Location: https://sampleservice.com/#id_token=SomeTokenValue&token_type=Bearer&expires_in=3600

Here is a comparison table of the possible outcomes that you would receive according to your regular expression:

|Description|Regex pattern|Outcome|
|---|---|---|
|Using a named group |id_token=(?&lt;IdToken&gt;[^&]+)&|SomeTokenValue|
|Using more than one named groups |id_token=(?&lt;IdToken&gt;[^&]+)&token_type=(?&lt;TokenType&gt;\w+)&|SomeTokenValue|
|Using a unnamed group |id_token=([^&]+)&|id_token=SomeTokenValue&|
|Mixing named and unnamed groups |id_token=([^&]+)&token_type=(?&lt;TokenType&gt;\w+)&|Bearer|




### Case Sensitivity

By default regular expressions are case-sensitive. If you need to ignore the casing when applying your regex pattern, you can include the **(?i)** option to make it case-insensitive. (See more information about regular expression options [here](https://msdn.microsoft.com/en-us/library/az24scfc(v=vs.110).aspx#options)). 
Example:

|Regex pattern|Outcome|
|---|---|
|**(?i)Test Studio** |will match **TEST studio** and **test STUDIO**|

If you need just part of the expression to be case-insensitive, you need to add **(?i)** in the begining of your case-insensitive pattern and add **(?-i)** where you need to turn the option off. If you skip the "turn-off" option **(?-i)**, then the **(?i)** option will be applied to the end of your pattern.
Example:

|Regex pattern|Outcome|
|---|---|
|**(?i)Test Studio(?-i) for APIs** |will match **TEST studio for APIs**, but not **Test Studio FOR apiS**|
|**(?i)Test Studio for APIs** |will treat the full pattern case-insensitive and will match **TEST studio for APIs** and also **Test Studio FOR apiS**|
|**Test Studio for (?i)APIs** |will treat only the "APIs" part of the pattern case-insensitive and will match **Test Studio FOR apiS**, but not **TEST studio for APIs**|

> Check the [Sample Project](/getting-started/sample-project) for more real-life examples of path expressions.


[1]: /img/features/full-value-path-option.png
[2]: /img/features/source-path-options.png
