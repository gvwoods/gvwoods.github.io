---
id: 211
title: Geo-Replication in Azure
date: 2018-07-09T12:44:45-04:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=211
permalink: /2018/07/09/geo-replication-in-azure/
image: /wp-content/uploads/2018/07/Geo-replication1.jpg
categories:
  - Azure
  - DBA
  - sql server
---
I was recently asked to look at creating a read-only copy of a SQL Server database in China, with the source being in the UK. . For on-premise, to get AlwaysOnAvailabilty with the replica being a read only copy we would need to be running Windows FailOver Clustering Server version and the database would need to be Enterprise Edition. However, this is easily set up in Azure, using Geo Replication and copies would only be seconds apart in replication.

I decided to do some testing. Geo replication is available at all price points in Azure, so for testing, I spun up a database in the Basic Pricing tier in the West US region. Once the database was available, I created a simple table with 4 rows of data and then confirmed the data existed. The next step was to go back in to Azure and under the newly created database resource, I clicked Geo-Replication. This opened another window that allowed me to choose a location. The picture above, shows all of the available locations. The blue hexagon is your primary database and the green hexagons are the available replication locations. For this one, I chose East Asia. The cost for this Geo-Replicated readable copy is the same as the primary copy. So in my case, each database was $5 per month.

&nbsp;

The Geo-Replicated database will have the same database instance name, but will have a different server name.  
<img loading="lazy" class="alignnone size-full wp-image-214" src="http://georgevwoods.com/wp-content/uploads/2018/07/Geo-replication2.jpg" alt="" width="913" height="241" srcset="http://georgevwoods.com/wp-content/uploads/2018/07/Geo-replication2.jpg 913w, http://georgevwoods.com/wp-content/uploads/2018/07/Geo-replication2-300x79.jpg 300w, http://georgevwoods.com/wp-content/uploads/2018/07/Geo-replication2-768x203.jpg 768w" sizes="(max-width: 913px) 100vw, 913px" /> 

As part of creating the new readable database, Azure will copy all of the data that is in the primary to the readable. Since I didn&#8217;t have much data, this process only took a minute or so. Once I got the notification that the readable was created, I connected via SSMS and was able to see the data. I then did some basic testing of deletes, inserts and updates. Obviously, the amount of data will make a difference, but as for speed, as soon as I hit execute in the primary database window and refreshed my select on the readable copy, the changes were there.

If you are looking for a read only copy of a SQL Server database, I definitely recommend Azure Geo-Replication. The whole process took less than 10 minutes to set up.

&nbsp;

&nbsp;