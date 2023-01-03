---
title: Overview
page_title: Verifications Overview - Test Studio Dev Documentation
description: Verifications in Test Studio Dev allow to test if an occurrence happened or did not happen as expected.
slug: recorder/verification-overview
position: 0
---

# Verifications

Automation is only the starting point of testing where the browser is manipulated automatically without tester intervention. Once you've automated the interaction, you still have to test something, such as measuring and recording that an occurrence happened or did not happen as expected. There are several ways to verify elements in Test Studio:

- <a href="/features/recorder/verifications/quick-verification" target="_blank">Quick Verification</a> - create an easy verification from the Quick Step menu when an element is highlighted.

- <a href="/features/recorder/verifications/advanced-verification" target="_blank">Advanced Verification</a> - craft a custom verification from the Sentence Verification Builder.

- <a href="/features/recorder/verifications/wait" target="_blank">Wait</a> - pause the test execution until the comparison is true.

- <a href="/features/recorder/verifications/extraction" target="_blank">Extraction</a> - extract an element's value and reuse it later in your test.

- <a href="/features/recorder/verifications/image-verification" target="_blank">Image Verification</a> - this feature is based on an element’s visual rendering rather than the properties or attributes of that element.

Verifications in Test Studio allow you to:

- Measure against multiple criteria at one time.
- Build these measurements in an interactive manner without code.
- Detect if elements are in a particular state (e.g. is visible, exists).
- Detect if attributes and properties compare with specific values.
- Verify content, attributes, styles, visibility, drop-down list selections, checkboxes, radio buttons, tables and Silverlight property values.

__Test Studio Dev__ implements verification through "sentences" that compare a portion of an element to a value, such as:

- textbox content is equal to 'order 2011'
- image path contains 'http://www.telerik.com'
- wait for element to exist

> Test Studio cannot read and verify against the contents of a PDF file loaded in the browser, as it does not have a DOM structure like a traditional web page. If you can store that information in a file type such as XLS, XML, CSV, or a SQL database, then you can use the <a href="/features/data-driven-testing/Overview" target="blank">Data Driving</a> feature. 
