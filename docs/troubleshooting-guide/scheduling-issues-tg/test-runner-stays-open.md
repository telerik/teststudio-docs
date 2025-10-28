---
title: Test Runner Stays Open
page_title: Test Runner Stays Open
description: "Understand why the Test Studio Test Runner process may remain open after closing Test Studio. Learn about the intended behavior, reasons for persistent processes, and how scheduled test execution affects Test Runner lifecycle."
position: 1
---
# Test Runner Stays Open

## PROBLEM

The Test Studio Test Runner process does not exit when you close Test Studio. 

## SOLUTION

This is by design: if there are still tests scheduled to run when you close Test Studio, or if the Test Runner was already running when you started Test Studio, the Test Runner will not exit when Test Studio closes. This is to ensure that Test Studio does not prevent scheduled test execution. 

