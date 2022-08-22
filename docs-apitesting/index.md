---
title: Index
page_title: Overview
description: "Progress® Test Studio® for APIs - Overview"
position: 1
---

# Overview

The new Test Studio for APIs helps customers verify the integrity and reliability of their APIs in an easy way and incorporate their API testing effort in their continuous testing and delivery process. Test Studio for APIs is used to determine whether APIs return the correct response for a broad range of commonly accepted requests, react properly to edge cases such as failures and unexpected inputs, as well as deliver the responses in an acceptable amount of time.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## Features

* Codeless API testing with build-in support for [Path expressions](/features/source-path-expressions) - a key goal of Test Studio for APIs is to enable customers to test their APIs without writing any code. You can cover various automation scenarios, make verifications and value extractions using XPath and JSONPath expressions.

* [Variable Management](/features/variables) - extract values from received http responses and store them in variables on a test or project level to be used for verifications or further http requests.

* [Verifications](/features/verifications) - use the built-in verifications to assert the results of your requests. Verify the properties of http responses like status code, response time, response body or headers. Compare them against expected values using various codeless text or numeric comparisons.

* [Value conversions](/features/steps/set-variable#Conversion) - you can transform your extracted variables using the built-in transformations like urlencoding, base64, md5, etc.

* Execution flow management - Handle complex scenarios with [Goto](/features/steps/goto) and [Wait](/features/steps/wait) steps. All test steps support [conditions](/features/condition) that allow you to control when the steps should be executed or skipped.

## Recording and Import

* [Record HTTP(S) Traffic](/features/record/http-traffic) - capture HTTP(S) traffic from within Test Studio for APIs. Import http(s) sessions directly as tests. You can make modifications to imported test requests to cover various alternative scenarios. Built-in shortcuts make it easy to make quick verifications for response headers, status or response time.

* [Import SAZ files](/features/record/import-http-traffic) - you can import SAZ files with already captured Fiddler traffic and import them as tests.

## CI Server Integration

* [CI Server Integration](/advanced-topics/ci-server-integration) - the included [command line interface](/features/command-line/overview) allows easy integration with most existing continuous integration servers (any CI server that supports executing command line commands can run Test Studio for APIs). [Command-line parameters](/features/command-line/command-line-parameters) support allows switching the values of key variables according to the target environment.

* [Test Results](/features/test-results) - the junit and XML test results support allows collecting and analyzing test results with most CI servers.

__See Also:__

* [Project Explorer](/features/project-explorer)
* [HTTP Requests](/features/steps/http-request)
* [Steps](/features/steps/overview)
* [Verifications](/features/verifications)
* [Working with variables](/features/variables)
* [Test Results](/features/test-results)
* [Record HTTP(S) Traffic](/features/record/http-traffic)
* [Import HTTP(S) Traffic](/features/import/http-traffic)
* [Advanced Topics](/advanced-topics/ci-server-integration)
