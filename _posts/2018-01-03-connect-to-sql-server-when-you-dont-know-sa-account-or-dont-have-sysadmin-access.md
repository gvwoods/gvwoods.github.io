---
id: 138
title: 'Connect to SQL Server when you don&#8217;t know SA account or don&#8217;t have sysadmin access'
date: 2018-01-03T12:55:17-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=138
permalink: /2018/01/03/connect-to-sql-server-when-you-dont-know-sa-account-or-dont-have-sysadmin-access/
image: /wp-content/uploads/2018/01/saPass.jpg
categories:
  - DBA
  - sql server
---
**Below are the steps you need to perform to grant SYSADMIN access to a user in SQL Server in case you are completely locked out.**

1. Download PSexec to connect using SQL Server Management Studio using the NT Authority\System

<span style="color: #3d85c6;">Download PsTools from https://download.sysinternals.com/files/PSTools.zip</span>  
 <span style="color: #3d85c6;">Unzip the content and copy PsExec.exe to C:\Windows\System32</span>

2. Stop the SQL Server and SQL Server Agent services on the server.

3. Open a cmd prompt window as administrator and navigate to SQL Server&#8217;s Binn directory. You may need to adjust your path based on your install location.

<span style="color: #3d85c6;">ex. C:\Program Files\Microsoft SQL Server\MSSQL11\MSSQL\Binn</span>

4. Once you are in SQL Server&#8217;s Binn directory run the &#8216;sqlservr -m&#8217; command to start SQL Server in single user mode as shown below. Had to add the location of the ERRORLOG

<span style="color: #3d85c6;">sqlservr -m -e C:\Program Files\Microsoft SQL Server\MSSQL11\MSSQL\Log\ERRORLOG;</span>

**If it&#8217;s a named instance:**  
 <span style="color: #3d85c6;">sqlservr -m -s <instancename> -e C:\Program Files\Microsoft SQL Server\MSSQL11.SERVICECORE\MSSQL\Log\ERRORLOG;</span>

After the SQL Server instance was started in single user mode, I was receiving logon errors form other users that were trying to logon from the application, when it was restarted in single user mode. I ignored the errors and moved on.

5. Execute PsExec &#8211; may need to adjust the &#8221; marks and file locations

<span style="color: #3d85c6;">run cmd as administrator</span>

<span style="color: #3d85c6;">PsExec -s -i &#8220;C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\ManagementStudio\Ssms.exe&#8221;</span>

The above command will launch SQL Server Management Studio and gives you a “Connect to Server” window and the User Name will be pre-populated with NT AUTHORITY\SYSTEM

<img loading="lazy" class="alignnone wp-image-141 " src="http://georgevwoods.com/wp-content/uploads/2018/01/ssms.jpg" alt="" width="778" height="409" srcset="http://georgevwoods.com/wp-content/uploads/2018/01/ssms.jpg 1154w, http://georgevwoods.com/wp-content/uploads/2018/01/ssms-300x158.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/01/ssms-768x403.jpg 768w, http://georgevwoods.com/wp-content/uploads/2018/01/ssms-1024x538.jpg 1024w" sizes="(max-width: 778px) 100vw, 778px" /> 

6. Click Connect and then go in to Security > Logins and add your account as a sysadmin

7. restart the sql server services

&nbsp;

&nbsp;

&nbsp;