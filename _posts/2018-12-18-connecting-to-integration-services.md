---
id: 479
title: Connecting to Integration Services
date: 2018-12-18T10:58:20-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=479
permalink: /2018/12/18/connecting-to-integration-services/
image: /wp-content/uploads/2018/12/integrationerror.jpg
categories:
  - Business Intelligence
  - DBA
  - sql server
---
This may not have been as much of an issue in the past, when the installation of SQL Server Management Studio was bundled with your SQL Server install, but now that they are decoupled, people will most likely see this error more often. The error I am talking about, is when you try connecting to Integration Services from SSMS and you are not using the same level of SSMS and Integration Services. For instance, the error in the screenshot in the header, is when I was trying to connect to 2016 Integration Services with SSMS 17.9. To fix the issue, I had to install SSMS 2016 and then I was able to connect. Hopefully, this is something that may be fixed in the future.