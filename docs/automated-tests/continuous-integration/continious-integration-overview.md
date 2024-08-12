---
title: Continuous Integration Testing 
page_title: Telerik Testing in Continuous Integration Environments
description: "Implement Telerik Test Studio Tests in Continuous Integration Environments"
position: 0
---
# Test Studio Tests in Continuous Integration Environments

Continuous Integration (CI) and Continuous Delivery/Continuous Deployment (CD) practices are essential in modern software development. The CI/CD pipeline is a crucial part of the DevOps lifecycle nowadays which cannot be complete without testing phase. And this is where you can implement the functional UI tests designed with Test Studio. 

This article provides the requirements from Test Studio perspective to setup the execution of functional UI tests as part of an automated pipeline.

* [Requirements to cover on the execution machine](#execution-machine-requirements)
* [The setup in overall](#setup-automated-testing-agents)
* [Examples for setting up pipeline in most common CI tools](#examples-of-implementing-test-studio-tests-in-different-ci-pipelines)

## Execution Machine Requirements 

1. Active user session.
1. CI agent app running in console mode. 
1. Test Studio installation - minimum the Test Studio Run-time edition. 
1. Latest browser or tested WPF/Desktop application installed. 

## Setup Automated Testing Agent Machines

1. Log onto the build machine (from Test Studio perspective we also call it testing or execution machine) using an account with permissions needed to run the CI build agent.

1. Install the CI build agent from the CI tool in use. 

1. Run the CI agent in console mode - use command line or a shortcut link, follow the instructions from vendor. 

    > __Important!__
    > __Do not run the CI agent as a service__.

1. Install Test Studio software on the build machine - the minimum requirement is <a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Test Studio Run-time Edition</a>.

1. Leave the machine running and logged into the account. 

1. Most UI tests require active desktop session. Exception are the web tests executed in headless mode. 

> __Tip__
> Keeping an active user session is always a challenge. Thus we, from Test Studio, implemented few options to help in controlling the user session on the testing machines. These are available in the <a href="/advanced-topics/build-server/ts-test-runner-app" target="_blank">Test Studio Test Runner application</a> which gets installed with the Run-time Edition. 

## Examples of Implementing Test Studio Tests in Different CI Pipelines

Find out the desired type of pipeline and follow the instructions on how to implement Test Studio test runs in it. 

* <a href="/advanced-topics/build-server/azure-devops" target="_blank">Azure DevOps Classic Pipeline</a>
* <a href="/advanced-topics/build-server/jenkins-ci" target="_blank">Jenkins CI</a>
* <a href="/advanced-topics/build-server/team-city-builds" target="_blank">TeamCity</a>
* <a href="/advanced-topics/build-server/bamboo" target="_blank">Bamboo</a>
* <a href="/advanced-topics/build-server/cruise-control.net-builds" target="_blank">CruiseControl .Net</a>
