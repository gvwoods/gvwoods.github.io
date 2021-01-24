---
id: 309
title: 'Migrate SQL Server Database to Azure SQL Database using Data Migration Assistant &#8211; part 1'
date: 2018-08-29T14:40:56-04:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=309
permalink: /2018/08/29/migrate-sql-server-to-azure-sql-server/
image: /wp-content/uploads/2018/08/082918_1440_MigrateSQLS7.png
categories:
  - Azure
  - sql server
  - Uncategorized
---
We will be using the Data Migration Assistant to assess and then migrate an on-prem SQL Server 2012 SP2 database to an Azure SQL Database

<span style="font-size: 14pt;"><strong>Part 1: Download and install Data Migration Assistant<br /> </strong></span>

To install DMA, download the latest version of the tool from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53595), and then run the **DataMigrationAssistant.msi** file.

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS1.png) 

Click next

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS2.png) 

Accept the license agreement

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS3.png) 

Click install

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS4.png) 

Wait for the install to complete

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS5.png) 

Check the box beside Launch Microsoft Data Migration Assistant and click Finish

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS6.png) 

<span style="font-size: 14pt;"><strong>Part 2: Open Data Migration Assistant and create assessment<br /> </strong></span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS7.png) 

We will now start with assessing our on-prem SQL Server

  1. Click the +New icon and select Assessment project type
  2. Give your assessment a name
  3. We will leave the Source server type and Target server type as is.
  4. Click create

![](http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS8.png) 

<p style="margin-left: 18pt;">
  I left the defaults checked and clicked next
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS9.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  Fill in the server name and authentication type. *Notice that the credentials used to connect must be a member of the sysadmin role
</p>

<p style="margin-left: 18pt;">
  Click connect
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS10.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  Choose the sources and click add. I am only interested in the CentralDB database at this time
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS11.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  If you are satisfied with the sources that you have added, click Start Assessment
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS12.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  Obviously, the assessment run time depends on how many and what size of the sources
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS13.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  When the assessment completes
</p>

<p style="margin-left: 18pt;">
  You can see the results on the screen or you can export the report as a json or csv file.
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS14.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  In this example, you can see that there are 3 Unsupported features and 1 Partially supported feature.
</p>

<p style="margin-left: 18pt;">
  With each issue the details section will give the impact. Recommendation and more info
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS15.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  One last screenshot to show the assessment options
</p>

<p style="margin-left: 18pt;">
  You can open, restart or delete an assessment
</p>

<p style="margin-left: 18pt;">
  <img src="http://georgevwoods.com/wp-content/uploads/2018/08/082918_1440_MigrateSQLS16.png" alt="" />
</p>

<p style="margin-left: 18pt;">
  <strong>In <a href="http://georgevwoods.com/2018/08/31/migrate-sql-server-to-azure-sql-server-using-data-migration-assistant-final-steps/">part 3</a>, we will look at Migrating a SQL Server database to Azure SQL Database.</strong>
</p>

&nbsp;

&nbsp;

&nbsp;

&nbsp;