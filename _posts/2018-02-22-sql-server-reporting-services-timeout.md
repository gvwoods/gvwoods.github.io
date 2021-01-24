---
id: 164
title: SQL Server Reporting Services Timeout
date: 2018-02-22T14:19:16-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=164
permalink: /2018/02/22/sql-server-reporting-services-timeout/
image: /wp-content/uploads/2018/02/timeout.jpg
categories:
  - Business Intelligence
  - sql server
  - Uncategorized
---
The other day we ran in to an issue where the report was running 30 minutes, this may be the only report that we have that runs this long, but then it fails. The only error message was &#8220;Report processing has been canceled by the user. (rsProcessingAborted), but after checking, no one canceled the report processing. What just happened?

It was determined that the Report timeout option was set to “Use the default setting” like most of our reports are.

<img loading="lazy" class="alignnone size-full wp-image-169" src="http://georgevwoods.com/wp-content/uploads/2018/02/default.jpg" alt="" width="501" height="226" srcset="http://georgevwoods.com/wp-content/uploads/2018/02/default.jpg 501w, http://georgevwoods.com/wp-content/uploads/2018/02/default-300x135.jpg 300w" sizes="(max-width: 501px) 100vw, 501px" /> 

&nbsp;

Well, where is this default setting and what is it set to? The default settings timeout is set in the **site settings** page of your SQL Services Reporting Services and it was set to 1800 seconds or as you guessed, 30 minutes.

<img loading="lazy" class="alignnone size-full wp-image-168" src="http://georgevwoods.com/wp-content/uploads/2018/02/site.jpg" alt="" width="774" height="631" srcset="http://georgevwoods.com/wp-content/uploads/2018/02/site.jpg 774w, http://georgevwoods.com/wp-content/uploads/2018/02/site-300x245.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/02/site-768x626.jpg 768w" sizes="(max-width: 774px) 100vw, 774px" /> 

&nbsp;

You have two options to fix the the timeout issue.

1. Change the default settings timeout for the whole site in the site settings page.

2. Change the Report timeout setting just for that report. This is done by going to the report, clicking the … and choosing manage.

<img loading="lazy" class="alignnone size-full wp-image-166" src="http://georgevwoods.com/wp-content/uploads/2018/02/manage.jpg" alt="" width="615" height="364" srcset="http://georgevwoods.com/wp-content/uploads/2018/02/manage.jpg 615w, http://georgevwoods.com/wp-content/uploads/2018/02/manage-300x178.jpg 300w" sizes="(max-width: 615px) 100vw, 615px" /> 

You then scroll down to Advanced and either choose “Allow the report to run for (add amount of seconds here) seconds before timing out” and changing the seconds to a higher value that will allow the report to run or choose the “Allow the report to run indefinitely (no timeout)” option.

&nbsp;

<img loading="lazy" class="alignnone size-full wp-image-165" src="http://georgevwoods.com/wp-content/uploads/2018/02/opt3.jpg" alt="" width="466" height="231" srcset="http://georgevwoods.com/wp-content/uploads/2018/02/opt3.jpg 466w, http://georgevwoods.com/wp-content/uploads/2018/02/opt3-300x149.jpg 300w" sizes="(max-width: 466px) 100vw, 466px" /> 

Click Apply and your report should not complete.

&nbsp;

&nbsp;

&nbsp;