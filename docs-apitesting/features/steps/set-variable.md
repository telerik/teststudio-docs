---
title: Set Variable Step
page_title: Set Variable Step
description: "Progress® Test Studio® for APIs - Steps - Set Variable Step"
position: 3
published: true
---

# Set Variable Step

## Overview

The Set Variable Step creates a <a href="/features/variables">Runtime Variable</a> from another Variable. 


![Set Variable Step][1]


## Source and Source Path

Similar to the Verifications, the Source property of the Set Variable Step always points to a <a href="/features/variables">Variable Name</a>.
 You could use the Source Path property to specify JSONPath or XPath to extract parts from the Source Variable. See more about path expressions [here](/features/source-path-expressions).



## Variable

Specifies the name of the Variable to set. Note that if a Variable with the same Name exists on the Specified Level, its Value will be overwritten.



## Conversion

Use the Convert To property to convert the Source. This functionality is very useful when encoding parameters for access token.

![Set Variable Step][2]

> Currently supported conversions:
> 
> * url-encode
> * url-decode
> * base64-decode
> * base64-encode
> * MD5
> * SHA1
 



## Level

Set Variable can create Test Level (local) and Project Level (global) Variables. See <a href="/features/variables">Variables</a> for more information.



## Usages

* Save part of a large response in order to simplify the Verifications (usually to shorten the JSONPath)
* Save part of a response to be used from other tests (for example Access Token)
* Convert value to Base64



[1]: /img/features/steps/set-variable.png
[2]: /img/features/steps/set-variable-transformations.png



