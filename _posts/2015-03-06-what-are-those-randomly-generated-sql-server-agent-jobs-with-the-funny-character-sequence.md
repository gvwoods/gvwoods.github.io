---
id: 21
title: What are those randomly generated SQL Server Agent jobs with the funny character sequence?
date: 2015-03-06T12:52:00-05:00
author: George Woods
layout: post
permalink: /2015/03/06/what-are-those-randomly-generated-sql-server-agent-jobs-with-the-funny-character-sequence/
blogger_blog:
  - gvwoods.blogspot.com
blogger_author:
  - George Woods
blogger_permalink:
  - /2015/03/what-are-those-randomly-generated-sql.html
blogger_internal:
  - /feeds/27386963/posts/default/6170629512635030955
categories:
  - Reporting Services
  - SQL Agent Jobs
---
They some times look like 266102E5-EF3A-4D3B-B2AA-4907MM1DF28C or maybe D087318E-0C24-4895-9ECF-9530AA4D11B3 and they randomly show up in your Sql Server Agent list or do they randomly show up?  
Well they are your Reporting Services subscription jobs. The nice thing is that you can dissect the details in the job and then use those details in a master job plan.  
We recently did this so that our Report subscriptions were no longer time based, but became process based. We were originally scheduling the subscription to run based on what time we guessed the cube would finish processing and as you already know, guessing what time any process completes is a bad option. Once we took the details out of the randomly named job and put them in to the master job plan, we were able to deliver our subscription a lot earlier and without any manual process of checking to make sure it had all of the day&#8217;s details.