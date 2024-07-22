---
title: Anonymous Access Error When Connecting to Team Foundation Service
page_title: Anonymous Access Error When Connecting to Team Foundation Service
description: Anonymous Access Error When Connecting to Team Foundation Service. Error message - Resource not available for anonymous access. Client authentication required.
previous_url: /knowledge-base/project-configuration-kb/anonymous-access-error-when-connectiong-to-team-foundation-service
position: 1
publish: false 
---
#Anonymous Access Error When Connecting to Team Foundation Service#

Specific machines fail to connect to Team Foundation Service with the error:

**TF400813: Resource not available for anonymous access. Client authentication required.**

##Solution##

Install the following updates:

* <a href="http://visualstudiogallery.msdn.microsoft.com/a37e19fb-3052-4fc9-bef7-4a4682069a75" target="_blank">Team Foundation Server 2010 SP1 Object Model Installer</a>

* <a href="http://www.microsoft.com/en-us/download/details.aspx?id=29082" target="_blank">Visual Studio 2010 SP1 Team Foundation Server Compatibility GDR</a>