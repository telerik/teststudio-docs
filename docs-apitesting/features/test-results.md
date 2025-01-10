---
title: Test Results
page_title: Test Results
description: "Progress® Test Studio® for APIs - Test Results"
position: 0
published: true
---

# Test Results

Test Studio for APIs produces test results in the console output and in a xml file. 

## Console output generation

The application is reporting its state to the console output so the user can easily review them.

## File output generation

The general format for the test results file is XML. When running tests via command line, you can change the results format with the switch: `-f|--format` (See [Command Line Parameters](/features/command-line/command-line-parameters) for more info). 
The currently supported XML formats are: 

### Custom ApiTesting XML

This is the default result format produced by the CLI application.

### JUnit XMl

You can specify the switch `-f junit` to produce JUnit test results format. (Internally this will transform the default XML with XSLT to JUnit file format.) 