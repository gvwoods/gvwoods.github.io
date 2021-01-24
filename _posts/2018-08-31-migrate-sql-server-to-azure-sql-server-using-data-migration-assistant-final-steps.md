---
id: 328
title: 'Migrate SQL Server Database to Azure SQL Database using Data Migration Assistant &#8211; part 2'
date: 2018-08-31T13:06:19-04:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=328
permalink: /2018/08/31/migrate-sql-server-to-azure-sql-server-using-data-migration-assistant-final-steps/
image: /wp-content/uploads/2018/08/083118_1302_MigrateSQLS13.png
categories:
  - Azure
  - Cloud
  - DBA
  - sql server
---
The first two steps can be found at <http://georgevwoods.com/2018/08/29/migrate-sql-server-to-azure-sql-server/>

<span style="font-size: 14pt;"><strong>Part 3: Migration Assistant<br /> </strong></span>

<span style="font-size: 12pt;">Open the Data Migration Assistant and click on +New to start a new Migration<br /> </span>

<span style="font-size: 12pt;">Choose Migration<br /> </span>

<span style="font-size: 12pt;">Fill in the project name and keep the defaults for the other options and click Create<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS1.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">On the first screen, fill in the Server name and make your choice connection properties and click connect. Reminder the credentials used to connect must have Control Server permission<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS2.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">After connecting, choose the Source database. Keep Assess the database before Migration checked and click next<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS3.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">On the select target screen you have the option to either use an existing server to connect to and choose the target database or you can click on Create a new Azure SQL Database, which will take you to the Azure portal to create the new database.<br /> </span>

<span style="font-size: 12pt;">I went out to the Azure portal and created a new server and database for the migration. I then came back in to the DMA window and filled out the info requested and clicked connect. I am also using SQL Server Authentication to connect.<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS4.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">Choose the database that is the target and click next<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS5.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">Select the objects you want to migrate<br /> </span>

<span style="font-size: 12pt;">Check the Assessment and determine if you can fix the issue or uncheck the issue if you wish to not migrate the blocks<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS6.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">I also had an issue that I could not migrate some of the users, as they were in the form domain\user I just left these unchecked and will manually add any users to the new Azure SQL Server Database<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS7.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">Click generate sql script. This may take a little time to run<br /> </span>

<span style="font-size: 12pt;">Once completed, review the script. When you are satisfied with the script, click deploy schema.<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS8.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">The following screen will appear<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS9.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">On completion, check for errors and determine if you can move on. Once you are satisfied with the schema deploy, click Migrate Data<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS10.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">Check that all of your tables are marked as OK. Also, you can see at the top, that Microsoft strongly recommends that you temporarily change your Azure SQL database to performance level P15during the migration process. This database that I am migrating is so small, that I am going to leave it as is. Click Start data migration<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS11.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">The in-progress screen appears. You can also monitor some of the activity in the Azure portal. For instance, Resource Utilization and used space<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS12.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">Once the data migration has completed you will see at the bottom right that Migration is complete and the Duration<br /> </span>

![](http://georgevwoods.com/wp-content/uploads/2018/08/083118_1302_MigrateSQLS13.png) <span style="font-size: 12pt;"><br /> </span>

<span style="font-size: 12pt;">I then connected to the Azure SQL database using SQL Server Management Studio and ran some comparisons to the original source and detected no differences.<br /> </span>

<span style="font-size: 12pt;">Reminder, add any users in to the Azure SQL Server Database that were not automatically migrated.<br /> </span>

<span style="font-size: 12pt;">You have now completed the migration.</span>

&nbsp;

&nbsp;

&nbsp;