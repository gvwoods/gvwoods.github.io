---
id: 524
title: Correct settings to use Azure Blob Storage as a data source for the Power BI Service
date: 2019-01-26T09:50:39-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=524
permalink: /2019/01/26/connect-settings-to-use-azure-blob-storage-as-a-data-source-for-the-power-bi-service/
image: /wp-content/uploads/2019/01/Capture13.jpg
categories:
  - Azure
  - Power BI
---
This seems like it should be a no-brainer and it actually is, once you see it. However, I spent to much time this past week trying to figure out what I was doing wrong. What ended up leading me to the answer, was that I happened upon a screenshot from the Power BI Community that was showing the correct Connection settings. I will be doing a more detailed blog post about the set up of Azure Blob Storage and such, but for now, you can see the issue I was running in to.

When you first click on Azure Blob Storage the screen appears as such.

![](http://georgevwoods.com/wp-content/uploads/2019/01/012619_1450_Connectsett1.png) 

I went ahead and filled out the Account Name, chose my On-premises data gateway and chose anonymous, but got an error. I was going to list out all of the different errors I ran in to, and the various security changes I made on the Blob Storage, but why put you through all of that. 

Let&#8217;s get to the correct settings.

Fill out Account Name,  leave the field On-premises gateway equal to (none), change Authentication kind to Account key and input your Account Key. The issue I kept having was that I was putting my On-Premises gateway info in. I&#8217;m sure there may be a reason for this field, but so far, I haven&#8217;t found it.

 

![](http://georgevwoods.com/wp-content/uploads/2019/01/012619_1450_Connectsett2.png)