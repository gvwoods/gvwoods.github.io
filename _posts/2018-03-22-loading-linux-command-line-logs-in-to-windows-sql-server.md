---
id: 190
title: Loading Linux command line logs in to Windows SQL Server
date: 2018-03-22T14:22:15-04:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=190
permalink: /2018/03/22/loading-linux-command-line-logs-in-to-windows-sql-server/
image: /wp-content/uploads/2018/03/Capture1.jpg
categories:
  - DBA
  - Linux
  - PowerShell
  - sql server
---
We recently decided, for auditing reasons, that we would like to keep a record of all of the commands that were run on our linux machines and because of separation of duties, we would load those logs in to a SQL Server instance on Windows. Funny how I feel the need to avoid confusion and make sure I say were the SQL Server instance is.

**1. First, to be able to get the files I needed to be able to ssh to the linux servers. The easiest way to do this was using Putty**

  * Download Putty: Windows Installer version <https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html>
  * Run the Installer 
      * This will install the file pscp.exe which will be used to connect to Linux

I have separated out the two scripts. First one being the script to download the logs to Windows server and the second script is to load logs to SQL Server

**2. Download logs to Windows Server**

Since I am connecting to numerous linux servers, I am using a file to store the user names, passwords and server names and will iterate through each line in the file to connect and get the logs.

The files manager.txt and others.txt only contain the password used by that user.

Example server name file

<img loading="lazy" class="alignnone size-full wp-image-194" src="http://georgevwoods.com/wp-content/uploads/2018/03/servers.jpg" alt="" width="846" height="168" srcset="http://georgevwoods.com/wp-content/uploads/2018/03/servers.jpg 846w, http://georgevwoods.com/wp-content/uploads/2018/03/servers-300x60.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/03/servers-768x153.jpg 768w" sizes="(max-width: 846px) 100vw, 846px" /> 

** 3. Script to get server names, user names and passwords**

<img loading="lazy" class="alignnone size-full wp-image-196" src="http://georgevwoods.com/wp-content/uploads/2018/03/script1.jpg" alt="" width="646" height="339" srcset="http://georgevwoods.com/wp-content/uploads/2018/03/script1.jpg 646w, http://georgevwoods.com/wp-content/uploads/2018/03/script1-300x157.jpg 300w" sizes="(max-width: 646px) 100vw, 646px" /> 

&nbsp;

**4. Create SQL Server table** with the following columns – filename, command, workingDirectory, server, username and date

**5. Load logs in to SQL Server**

Example log file from Linux &#8211; As you can see, all of the commands came in as comma separated, but they were all on one line.

<img loading="lazy" class="alignnone size-full wp-image-193" src="http://georgevwoods.com/wp-content/uploads/2018/03/log1.jpg" alt="" width="1207" height="95" srcset="http://georgevwoods.com/wp-content/uploads/2018/03/log1.jpg 1207w, http://georgevwoods.com/wp-content/uploads/2018/03/log1-300x24.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/03/log1-768x60.jpg 768w, http://georgevwoods.com/wp-content/uploads/2018/03/log1-1024x81.jpg 1024w" sizes="(max-width: 1207px) 100vw, 1207px" /> 

&nbsp;

Using the Get-Content command changed the file to a usable format, we used the replace command to remove the space and the command number and we used Set-Content command to save this as a txt file

<img loading="lazy" class="alignnone size-full wp-image-192" src="http://georgevwoods.com/wp-content/uploads/2018/03/log2.jpg" alt="" width="1011" height="125" srcset="http://georgevwoods.com/wp-content/uploads/2018/03/log2.jpg 1011w, http://georgevwoods.com/wp-content/uploads/2018/03/log2-300x37.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/03/log2-768x95.jpg 768w" sizes="(max-width: 1011px) 100vw, 1011px" /> 

&nbsp;

<img loading="lazy" class="alignnone size-full wp-image-195" src="http://georgevwoods.com/wp-content/uploads/2018/03/script2.jpg" alt="" width="861" height="567" srcset="http://georgevwoods.com/wp-content/uploads/2018/03/script2.jpg 861w, http://georgevwoods.com/wp-content/uploads/2018/03/script2-300x198.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/03/script2-768x506.jpg 768w" sizes="(max-width: 861px) 100vw, 861px" /> 

**6. SQL Server table**

<img loading="lazy" class="alignnone size-full wp-image-191" src="http://georgevwoods.com/wp-content/uploads/2018/03/table.jpg" alt="" width="880" height="83" srcset="http://georgevwoods.com/wp-content/uploads/2018/03/table.jpg 880w, http://georgevwoods.com/wp-content/uploads/2018/03/table-300x28.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/03/table-768x72.jpg 768w" sizes="(max-width: 880px) 100vw, 880px" /> 

&nbsp;

&nbsp;

&nbsp;