---
title: Enable Deployment
page_title: How to Enable Deployment
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
published: false
---
# How to Enable Deployment

## PROBLEM

Deployment is the process of copying test assemblies, dependencies, and any other specified files to an "Out Directory." By default, the AppBase is the "Out Directory." If you try to use a Project/Solution that has not had the necessary data copied over, you will receive a similar error to below (this is a common reason for an error starting with System.IO.FileNotFoundException).

By enabling Deployment, you are telling Visual Studio to copy all files for the project to the Out Directory. When it is disabled, everything runs out of the root folder for the project/solution.

## SOLUTION

1.&nbsp; Open the project. 

2.&nbsp; Double-click the Test Settings file in use by the Project/Solution in the Solution Explorer. 

![Test Settings][1]

3.&nbsp; Click **Deployment** in the left column. 

4.&nbsp; Check **Enable Deployment**. 

![Enable Deployment][2]

5.&nbsp; Click **Apply**. 

> It will likely be necessary to Rebuild your project before running the test again.

[1]: /img/troubleshooting-guide/visual-studio-tg/enable-deployment/fig1.png
[2]: /img/troubleshooting-guide/visual-studio-tg/enable-deployment/fig2.png