---
id: 287
title: Overview of Connecting to Azure Analysis Services
date: 2018-07-19T15:14:09-04:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=287
permalink: /2018/07/19/overview-of-connecting-to-azure-analysis-services/
categories:
  - Azure
  - Business Intelligence
  - Cloud
---
With Azure Analysis Services Firewall off.

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC1.png) 

As admin account &#8211; Log in to Azure

Deploy model

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC2.png) 

**Connect with SQL Server Management Studio from laptop  
** 

With admin account &#8211; 3 options for connecting

Does not work  
![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC3.png)  
Does not work  
![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC4.png) 

Using MFA does work &#8211; screen pops up for password and then another for text message before gaining access. – we can see the model as well, since this account is an Analysis Services Admin  
![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC5.png) 

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC6.png) 

As my non-admin account same three options for connecting

Does not work

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC7.png) 

Works but am just typing password in

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC8.png) 

Works but connects just asking for password, not asking for mfa, however does not have access to any databases as they are not marked as an admin. They will need a role assigned

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC9.png) 

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC10.png)  
**Connect from Power BI  
** 

Using non-admin account

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC11.png) 

Using admin account – asks for password and MFA text

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC12.png) 

As admin create a read role in the model

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC13.png) 

Add non admin to read role

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC14.png) 

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC15.png) 

Try again to connect from Power BI using non admin account

Connection works with no MFA

![](http://georgevwoods.com/wp-content/uploads/2018/07/071918_1514_OverviewofC16.png) 

&nbsp;

&nbsp;

&nbsp;