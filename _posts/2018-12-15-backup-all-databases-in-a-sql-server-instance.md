---
id: 444
title: Back up all databases in a SQL Server instance
date: 2018-12-15T10:05:55-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=444
permalink: /2018/12/15/backup-all-databases-in-a-sql-server-instance/
image: /wp-content/uploads/2018/12/backup1.jpg
categories:
  - DBA
  - sql server
---
Here is one of my favorite time saving scripts, that I wanted to pass on. This script will back up all databases, except for the system databases.

I did not write this script. The author is Greg Robidoux and the original link is <a href="https://www.mssqltips.com/sqlservertip/1070/simple-script-to-backup-all-sql-server-databases/" target="_blank" rel="noopener">https://www.mssqltips.com/sqlservertip/1070/simple-script-to-backup-all-sql-server-databases/</a>

&#8212;beginning of script&#8212;&#8211;

DECLARE @name VARCHAR(50) &#8212; database name  
DECLARE @path VARCHAR(256) &#8212; path for backup files  
DECLARE @fileName VARCHAR(256) &#8212; filename for backup  
DECLARE @fileDate VARCHAR(20) &#8212; used for file name

&#8212; specify database backup directory  
SET @path = &#8216;D:\backups\&#8217;

&#8212; specify filename format  
SELECT @fileDate = CONVERT(VARCHAR(20),GETDATE(),112) + REPLACE(CONVERT(VARCHAR(20),GETDATE(),108),&#8217;:&#8217;,&#8221;)

DECLARE db\_cursor CURSOR READ\_ONLY FOR  
SELECT name FROM master.dbo.sysdatabases WHERE name NOT IN (&#8216;master&#8217;,&#8217;model&#8217;,&#8217;msdb&#8217;,&#8217;tempdb&#8217;) &#8212; exclude these databases

OPEN db_cursor  
FETCH NEXT FROM db_cursor INTO @name

WHILE @@FETCH_STATUS = 0  
BEGIN  
SET @fileName = @path + @name + &#8216;_&#8217; + @fileDate + &#8216;.bak&#8217;  
BACKUP DATABASE @name TO DISK = @fileName

FETCH NEXT FROM db_cursor INTO @name

END

CLOSE db_cursor  
DEALLOCATE db_cursor

&#8212;-end of script&#8212;-

The files in the back up directory. You can see the timestamp has been added.

<img loading="lazy" class="alignnone wp-image-450" src="http://georgevwoods.com/wp-content/uploads/2018/12/backupfiles.jpg" alt="" width="774" height="300" srcset="http://georgevwoods.com/wp-content/uploads/2018/12/backupfiles.jpg 805w, http://georgevwoods.com/wp-content/uploads/2018/12/backupfiles-300x116.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/12/backupfiles-768x298.jpg 768w" sizes="(max-width: 774px) 100vw, 774px" /> 

Output in SSMS

<img loading="lazy" class="alignnone wp-image-451" src="http://georgevwoods.com/wp-content/uploads/2018/12/backupoutput.jpg" alt="" width="805" height="480" srcset="http://georgevwoods.com/wp-content/uploads/2018/12/backupoutput.jpg 1129w, http://georgevwoods.com/wp-content/uploads/2018/12/backupoutput-300x179.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/12/backupoutput-768x458.jpg 768w, http://georgevwoods.com/wp-content/uploads/2018/12/backupoutput-1024x610.jpg 1024w" sizes="(max-width: 805px) 100vw, 805px" />