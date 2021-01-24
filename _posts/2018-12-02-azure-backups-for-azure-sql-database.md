---
id: 432
title: Backups for Azure SQL database
date: 2018-12-02T13:55:42-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=432
permalink: /2018/12/02/azure-backups-for-azure-sql-database/
image: /wp-content/uploads/2018/12/restore1.jpg
categories:
  - Azure
  - Cloud
  - DBA
  - sql server
---
All backups are automatically taken and at no additional charge. These backups are also automatically replicated to a paired data center. You will not have to configure anything. However, if your compliance rules require you to keep backups longer than the 35 days, you can set up long term retention for a fee. This retention can be up to 10 years.

**Below are the details for the backups**

A Database can be restored to any point in time.

On creation of the Azure SQL database, a full backup is taken.

After the initial backup, the backup schedule is as follows:

  * Full backups are taken once a week.
  * Differential backups are generally taken every 12hrs, depending on size and activity
  * Transaction log backups are taken every 5 minutes.

Default Retention period for the backups

  * Basic tier is 1 week
  * Standard and Premium both last for 5 weeks

&nbsp;

I will be following up with another blog post showing an example restore.