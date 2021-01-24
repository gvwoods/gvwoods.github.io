---
id: 206
title: Creating a RunAsAccount in Azure for Azure Automation
date: 2018-04-04T17:36:57-04:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=206
permalink: /2018/04/04/creating-a-runasaccount-in-azure-for-azure-automation/
image: /wp-content/uploads/2018/04/automation.jpg
categories:
  - Azure
  - Business Intelligence
  - Cloud
  - SQL Agent Jobs
---
Warning: We have three different people with three different levels of security in our Azure tenant and only one of us could create this account.

Person 1: Is the owner of a Resource group and can create items in the resource group, including the Automation Account and Runbooks, but can not create the RunAsAccount

Person 2: Is the tenant admin and can do what Person 1 can do and a lot more, but does not have permissions to create a user in Azure AD, so can not create the RunAsAccount either.

Person 3: Has all of the permissions as person 2, but is also able to create users in Azure AD, so he was the only one that was able to create the RunAsAccount.

**Below are the steps that he followed to create the account**

1. In the Azure portal, click All resources. In the list of resources, select the Automation account from the list of Automation accounts.

2. In the left-hand pane, select Run As Accounts under the section Account Settings.

3. Select Azure Run As Account. After selecting the Add Azure Run As Account, a pane appears and after reviewing the overview information, click Create to proceed with Run As account creation.

4. While Azure creates the Run As account, you can track the progress under Notifications from the menu. A banner is also displayed stating the account is being created. This process can take a few minutes to complete.

**Since we only wanted the RunAsAccount to have permissions to certain Resource groups and not the whole subscription, we followed the steps below.**

Limiting Run As account permissions &#8211; To restrict what the RunAs service principal can do, you can remove the account from the contributor role to the subscription and add it as a contributor to the resource groups you want to specify.

1. In the Azure portal, select Subscriptions and choose the subscription of your Automation Account. Select Access control (IAM) and search for the service principal for your Automation Account (it looks like _unique identifier). Select the account and click Remove to remove it from the subscription.

2. To add the service principal to a resource group, select the resource group in the Azure portal and select Access control (IAM). Select Add, this opens the Add permissions page. For Role, select Contributor. In the Select text box type in the name of the service principal for your Run As account, and select it from the list. Click Save to save the changes. Do this for the resources groups you want to give your Azure Automation Run As service principal access to.

&nbsp;

&nbsp;

&nbsp;